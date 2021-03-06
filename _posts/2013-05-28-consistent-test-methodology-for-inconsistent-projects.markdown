---
layout: post
title: "Consistent Test Methodology for Inconsistent Projects"
date: 2013-05-28 23:43
---
How do you start introducing some testing if you have a huge group of existing
projects, for the most part all implemented using different languages and
technologies? That's the problem I've been poking at recently. The first issue
is that none of the technology choices were made with testability in mind. And
I don't want to have to go through and run a bunch of code refactoring and 
reorganization just to start testing. I would much rather start testing, and
then start introducing changes to make things easier to test and to increase
the coverage. The second issue is that we're pretty sure there are some major
architectural changes and redesigns coming in the short term. So to dig in and
harness up the guts of a bunch of systems we know will be changing really
shortly anyway also doesn't seem like a fantastic idea. Plus some of the
changes are more about the operating environment than the code itself, and
a bunch of unit tests won't necessarily help us figure out if the web services
break when we move from MySQL 5.5 to 5.6.

The most obvious and brute-force way would be to recreate the whole end-to-end
environment and create some system tests for it. I think that would be too
brute-force though. I would like our first step to provide some tools that
would be useful to developers and the infrastructure folks. A whole end-to-end
environment might be useful for infrastructure, but would be a burden for
development. Even if this were running up on AWS, imagine having to spin up
a dozen instances and wait for them to initialize just so you could test your
one change. And the system as a whole definitely wasn't built with testability
at the granularity of the entire infrastructure in mind. So good luck being
able to hit even a small set of the conditions the running systems are
subjected to.

No, what we needed to start were a few automated acceptance tests at the
granularity of the individual architecture components. Fortunately, cause much
of the process before was run off manual QA there are collections of test
cases floating around for lots of the components. And there's frequently even
a description on a wiki page of how to configure a QA environment for a given
component (for example how to setup a database, configure Tomcat, and install
and run a web service). So now it's just a matter of being able to script all
that up.

Since I wanted these tests to be useful both for development time checks and
infrastructure validation that meant they needed to run on an environment as
close to production as possible. But setting up a bunch of testing
environments introduces a whole other set of problems potentially as large as
the set we're trying to solve. Spinning up the instances in the cloud might
work, but also introduces a different level of complexity. I wanted
something that a developer could have available right in their project
checkout they could use to validate their work as they go along and ensure
there won't be any surprises when trying to run in production. Fortunately,
that's exactly what [Vagrant](http://www.vagrantup.com/) is meant to provide.

With Vagrant and [VirtualBox](https://www.virtualbox.org/) on a development
machine it's easy to spawn a VM running the same version of CentOS we're
running in production. The instructions for setting up a QA environment
become
[provisioning scripts](http://docs.vagrantup.com/v2/provisioning/index.html)
for the Vagrant config, which automatically get run when the VM launches.
The automation for the test cases themselves or loading data need to be
handled on a case-by-case basis, but with the ability to sync files between
host system and VM and automatically configure port forwarding into the VM
it makes it much simpler to bundle everything into a single command.

Cause we're testing at the same granularity at which these projects are
deployed, we don't have to refactor the projects before we can
start automating some testing. The projects already have well defined input
and output points, which is how they communicate with the rest of the 
infrastructure, so we just latch onto those. Now, admittedly, the service
contracts for lots of the projects are fuzzy at best. Cleaning those up is one
of our medium term goals. But at least now we can start with testing in place
and then start changing stuff.

And if the infrastructure folks want to try running on a different distro,
or using a different version of a package, they also now have the tools to
check changes without having to run things through QA.
Make the necessary changes on the VM and then run the script to make sure
nothing has broken.

For this to start looking like a proper continuous delivery test setup we
should be driving the setup of the VM using the same configuration as we use
in production, which is why we're also working on swapping to a more robust
infrastructure automation system than we have currently. For example, Vagrant
allows Chef or Puppet for provisioning instead of using a shell script. And
instead of using the synced filesystem to move data back and forth, the system
under test should be deployed using the same tools and process as the deploy
to production. But at least there's movement in the right direction now.
