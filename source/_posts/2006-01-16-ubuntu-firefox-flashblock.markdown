---
comments: true
date: 2006-01-16 15:50:47
layout: post
slug: ubuntu-firefox-flashblock
title: Ubuntu + Firefox + Flash(block)
wordpress_id: 608
categories:
- General
---

I don't use Flash normally, but I installed it (with the [flashblock plugin for Firefox](http://flashblock.mozdev.org/) of course) so that I can fool around with [Google Analytics](http://www.google.com/analytics/), which renders views in little flash applets. Cool, as much as I don't like Flash normally it's a nice path to transition to richer functionality on the client side later on, so it makes sense in this context. The problem was that I wasn't getting any text in Flash. I found [the answer on the OpenLaszlo wiki](http://wiki.openlaszlo.org/Installation_Instructions) quickly enough, the font that Flash uses is in the ghostscript package:


> apt-get install gsfonts-x11


Mmmm, graphs with labels now. Peachy. And of course I've spent some time mucking around with [Google Video](http://video.google.com/) as well. But we don't need to talk about that. I have just one thing to say: [Robot Chicken](http://video.google.com/videosearch?q=robot+chicken).
