---
comments: true
date: 2006-01-24 01:27:28
layout: post
slug: bawk-bawk-bawk-bakawwwwk
title: Bawk Bawk Bawk Bakawwwwk!
wordpress_id: 612
categories:
- General
---

I use [Chicken](http://www.call-with-current-continuation.org/) every once in a while, particularly when fooling around with web stuff. They have some kick ass extensions : [basic HTTP](http://www.call-with-current-continuation.org/eggs/http.html), [more featurefull web server](http://www.call-with-current-continuation.org/eggs/spiffy.html), [XML query and generation](http://www.call-with-current-continuation.org/eggs/ssax.html). I first ran across it looking at some [modal web programming samples](http://www.double.co.nz/scheme/modal-web-server.html) and have continued to like it ever since. However I just 'apt-get chicken' installed the environment on my Ubuntu system only to find that the build was very very much out of date. Most of the extensions I installed failed to load into the interpreter cause names have changed or the extensions use new features. So I downloaded Chicken 2.2 source and installed from that in about 15 seconds.  Just figured I would post in case anyone run across problems with Chicken on Ubuntu when trying to just use chicken-setup to install eggs. If you're pointed at the same repositories I am you probably got a 1.6 build from 2004, that's the problem.
