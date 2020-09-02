---
layout: post
title: "Scaling Technology"
date: 2013-07-14 17:41
---
A few weeks ago Arte and Mario asked me to swing by to chat with folks participating in
<a href="http://momentum.mobilemonday.us/">the Momentum accelerator</a> to talk about 
scaling technology. While we were talking I pointed folks to a few posts and videos of 
talks I consider to be some of the root nodes of a lot of other conversations. I'm not
sure I've ever pulled this together before.

* [Allspaw/Hammond - 10+ Deploys Per Day](http://blip.tv/oreilly-velocity-conference/velocity-09-john-allspaw-10-deploys-per-day-dev-and-ops-cooperation-at-flickr-2297883)
* [Randy Shoup - Ebay's Architectural Principles](http://www.slideshare.net/deimos/randy-shoup-ebays-architectural-principles)
* [AKF Partners - Splitting Applications or Services for Scale](http://akfpartners.com/techblog/2008/05/08/splitting-applications-or-services-for-scale/)
* [High Scalability](http://highscalability.com/)
* [Netflix Tech Blog](http://techblog.netflix.com/)

That Allspaw/Hammond presentation is the most primary in my opinion. It's the talk
that lots of us consider to be the inflection point of the devops movement, when the
practice started to really gain visibility. What had previously been a random 
collection of techniques we didn't have a great way to refer to became "devops".
There's a ton of useful information in that presentation. Not just the overall
concepts of dev and ops working together with a different kind of coupling, but some
specific tools to make that happen like shared metrics, feature flags, and shipping
dark.

The presentation from Randy Shoup has also withstood the test of time fantastically
well. The four architectural principles are great top level items: partition
everything, async everywhere, automate everything, remember everything fails. And the
presentation from AKF Partners dives into a bunch more detail about how to partition
services so that you can just throw hardware at problems. That model also provides a
lot of the basis for most of the conversations I end up having about geographic 
distribution of services (which actually sounds exactly like a discussion about how
to design the I/O layer of an operating system, you just swap terminology).

The High Scalability and Netflix blogs provide great concrete examples of what some
of the problems and solutions look like. Principles are great, but like always
there's more than one way to do it. So it's great to have some concrete examples to
poke through. Plus Netflix being one of the pioneers of the static AMI methodology
of infrastructure automation it makes their approaches particularly strongly 
opinionated.

The platforms themselves have changed the level of abstraction you need to work at
when putting this stuff into practice. Thanks to MongoDB and Riak we don't have to
wrapper tons of instances of MySQL or Postgres to make a datastore that scales 
horizontally. And thanks to services like Elastic Beanstalk, Heroku, and EngineYard
we don't have to pay as much attention to how to distribute load across multiple
application servers. But even though you can count on your platform to remove a 
bunch of the details in some cases, it's a good idea to understand the principles.
First of all cause it's possible to misuse the platform and end up not
getting the full advantage you could. But also because platforms can only help out
so far. Eventually you need to crack open the abstractions and either continue
with an application optimized line of evolution, or figure out how to wrapper
additional layers of capability around what the base platform provide. In either
case at least being aware of the principles your underlying platforms are working
on will pay back hugely.
