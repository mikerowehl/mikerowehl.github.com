---
comments: true
date: 2005-01-11 16:31:59
layout: post
slug: rss-subscription-synchronicity
title: RSS Subscription Synchronicity
wordpress_id: 389
categories:
- Open Source
---

Apparently Dave Winer [has been thinking](http://archive.scripting.com/2005/01/11#theSolutionToTheYahooProblem) about the [same problem I was](http://www.bitsplitter.net/blog/index.php?p=388) in terms of RSS subscriptions. I'm in favor of something a little simpler than what he described, but I can certainly see value in what he's talking about. I emailed Dave to see if we could start trying to spin up something like this. In my mind one of the important aspects is that all the code running behind this should be open sourced. Code has a way of allowing problems to be wrung out quickly, discussions get a lot shorter and consensus is more absolute. I think it's the only way to end up with the kind of trust that would be needed to get most publishers to use a service like this. It also guarantees that if the current service provider does something to lose that trust, another source can come in to replace them without too much effort. Of course, the ideal is that everyone decides to trust the same source, and that a users preference setting is used at every site they go to.

Effectively what I had proposed was using the service as a namespace to store cookies in, and return very specific pages based on the settings in those cookies. Of course the problem is more generalizable. The setting of cookies and generation of returned pages could all be controlled from the publishers site, and we end up with something like a preferences engine. Which I'm sure is much better done with something like [XRI/XDI](http://xrixdi.idcommons.net/) than cookies and Javascript.  Problem is, I have no idea how a system would be architected using that kinda stuff. So if someone does, please jump in the conversation and enlighten us.
