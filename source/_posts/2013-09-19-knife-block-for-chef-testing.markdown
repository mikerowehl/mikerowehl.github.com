---
layout: post
title: "knife-block for Chef Testing"
date: 2013-09-19 12:17
comments: true
categories: 
- Engineering
- Infrastructure Automation
- Continuous Delivery
- Operations
---
A few weeks ago [Nathen Harvey](https://github.com/nathenharvey) was kind
enough to stop by and give us a critique of how we do Chef automated testing
and some workflow suggestions. We had been using chef-solo
to do some of the recipe development and automated testing, but all our real
deployments were done using chef-client. And the differences
between solo runs and chef-client runs kept biting us. We had seen the stuff
Lookout Mobile has done to 
[run a VM for the chef server](http://hackers.lookout.com/2012/04/cookout-at-lookout-with-chef/)
in addition to the node during testing. But that seemed like an awful lot of
overhead. Fortunately Nathen gave us the awesome hack of using different
organizations for the different developers of chef rules, different
organizations for CI, and then the production organization. That gives us
complete isolation of the different working areas, but still keeps setup
relatively simple. w00T!

His suggestion was to use
[the knife-block plugin](https://github.com/greenandsecure/knife-block)
to make swapping around between organizations easier. Definitely an awesome
tool, and very useful. But we ran into a few issues because 
knife-block uses a different method for finding it's knife.rb file than the
knife command does. So I pushed up a
[fork of the original knife-block code](https://github.com/mikerowehl/knife-block)
with a change to how it picks up the configuration location. This version uses
the Chef::Knife config loader to find the actual configuration being used,
and uses that directly. In the original version it borrowed a function from
Chef, but that function tried to find knife config by looking for a .chef
directory somewhere in the parent directories on the filesystem. The real
Chef config loader looking in a bunch of additional places.
So the result was that if you had your
config in ~/.chef and ran your knife block commands from your home dir it worked
fine, but if you cd into /tmp suddenly your knife block commands
would freak out.

Once I dug in and saw what was going on, I figured it would be pretty easy to
fix up. After looking at the Chef code it became obvious why the knife-block
stuff did things the way it did. I hate to have to monkey patch to get things
to work, but the change is actually pretty trivial. I ended up
[injecting a get_config_file method](https://github.com/mikerowehl/knife-block/blob/494b8c08a45c17c1335a97e4a6a6b08ecdc73c11/lib/chef/knife/block.rb)
into Chef::Knife so that once I constructed a Knife object I could ask it for
the location of the chef config file. Now if knife itself works, I'm sure 
knife-block will end up pulling config from the same location. Useful for when
I need to login to the CI server and poke around to do some debugging 
(Bamboo stores the test files outside of the home directory of the bamboo
user in our configuration).

For the testing itself we use some Vagrantfiles with definitions of the
different server types we have. Knife-block provides a nice easy way for me
to test against an mrowehl organization, and then use a devops-test 
organization for some automated validation, and finally swap to the prod
organization to push stuff up live. So of course I want to be able to use
the Vagrantfile when I'm testing locally and developing recipes, and use the
same Vagrantfile on the Bamboo server with the devops-test organization to
validate that everything is working. I didn't want to have to go in and edit
the chef-client provisioner config to swap organizations though, and using
something like environment variables to drive it just seemed really ugly.
Fortunately we ran across 
[this post about pulling vagrant chef-client config from knife.rb](https://coderwall.com/p/dt1idw)
and ended up putting together
[our Vagrantfiles so they automatically follow where knife-block is pointed](https://gist.github.com/mikerowehl/6631396).
Together with the changes in the Vagrant 1.3 series releases to automatically
remove node and client from the server when you do a 'vagrant destroy' it
makes for an awesome testing setup. Just use knife block to swap around to
different organizations and up/destroy your boxes as much as you want,
your wanton path of destruction just gets all swept up automatically behind
you.

With the vagrant config hackery in place it doesn't matter what
organization we want to test against, the text
of the Vagrantfile can stay the same as long as knife is pointed to the right
place. That made it pretty trivial to put together a simple
[wrapper Rakefile to clear and populate the organizations](https://gist.github.com/mikerowehl/6631010).
With those wrappers all our Bamboo server has to do is:

* grab the latest from our chef-repo with git
* 'knife block use devops' to swap to our test organization
* 'rake delete\_all' to clean out the test organization
* 'rake upload\_all' to put all the new cookbooks in place
* 'vagrant up' for the actual test
* and then a run always ending task to 'vagrant destroy -f'

Fortunately the vagrant up command returns the exit status of the chef-client
run as the status for the command, so picking up failures is pretty trivial.

Of course, this stuff isn't perfect. The tests always run in our 'dev'
environment, which has the cookbook versions unpinned. That's how we can clean
out and reload the organization each time without it causing trouble. Of
course if you had pinned cookbook versions you would have to add in some logic
to make sure you could load the proper version each time you reload. But for
our current level of complexity, just knowing that the latest batch of changes
doesn't completely break is an awesome start.

It's not quite ready for a release yet, but I've also got
[some Packer templates](http://www.packer.io/) which converge a node using
chef-client and export the Vagrant friendly box so I can distribute the VM.
Once I have them cleaned up a bit I'll post those too.
