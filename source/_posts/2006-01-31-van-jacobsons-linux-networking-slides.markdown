---
comments: true
date: 2006-01-31 16:34:39
layout: post
slug: van-jacobsons-linux-networking-slides
title: Van Jacobson's Linux Networking Slides
wordpress_id: 617
categories:
- Open Source
---

The [slides from Van Jacobson's LCA2006 presentation](http://vger.kernel.org/~davem/cgi-bin/blog.cgi/2006/01/30#van_slides) are online. They talk about an evolution to the Linux networking stack targeted at taking into account multicore systems. If I had to summarize the presentation I would steal the title from slide 16: "The end of the wire isn't the end of the net".


> On a uni-processor it doesn't matter, but on a multi-processor the protocol work should be done on the processor that's going to consume the data.

This means ISR and Softint should do almost nothing and Socket should do everything.


The slides are excellent and lay out the issue very clearly, but I would also recommend checking out [DaveM's comments on net channels](http://vger.kernel.org/~davem/cgi-bin/blog.cgi/2006/01/27#vj_channels). It was his writeup that turned me on to the presentation.
