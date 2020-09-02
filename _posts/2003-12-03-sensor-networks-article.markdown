---
comments: false
date: 2003-12-03 20:49:56
layout: post
slug: sensor-networks-article
title: Sensor Networks Article
wordpress_id: 13
categories:
- Mobile Computing
---

There's [an article](http://www.wired.com/wired/archive/11.12/intel.html) in Wired about Intel's play to get wireless sensors shrunk down over coming years. I've been working with some people looking to make products using existing sensor networks technologies. I've gone to a couple of sensor network specific workshops and forums in the area, including the Hitachi/Stanford Workshop on Wireless Sensor Networks. It's very interesting technology, and I can definitely see where systems of this sort would have great applications. But the hardware that's available now for sensor networks is pretty expensive still. The systems aren't that small. They do provide wireless networking capability, which is definitely a differentiator in a device of that size and cost. Even the researchers seem to think that the technology is still in the formative stage. It's definite that the mesh networking still needs to be worked through to a great degree. But even leaving that aside I have some concerns.

I'm starting to try to familiarize myself with the TinyOS system and get a feel for what the extents of the system can be. In particular, should we be looking to use something else in the initial implementation of our prototypes? We're not really sure what the data throughput requirements will be for the application yet, and we don't have a lot of slack to play with when the peak throughput of the wireless interface is 30 or 40 Kbps. I guess only time will tell. But if others out there are looking at using the MOTES platform in upcoming projects and looking at the same issues, please [mail me](mailto:miker@bitsplitter.net). I would be interested in exchanging ideas.
