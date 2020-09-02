---
date: 2006-08-23 23:05:49
layout: post
title: http_load for Request Replay
---

The [presentation that Rasmus gave at OSCON](http://talks.php.net/show/oscon06/0) this year seems to have kicked some ass. I missed the conf, but got a bunch of interesting info from the slides. In particular I hadn't used [http_load](http://www.acme.com/software/http_load/) before. Part of what I've been doing at AdMob is taking a look at performance and scaling, so that was a great find. It's exactly the set of controls and measurements I normally start out with, and it really does run very efficiently in terms of not loading down the system that http_load is running on. 

Just about the only thing that didn't work the way I wanted was the random selection from the url list file. I wanted to replay a set of traffic in order, so I [hacked up an -orderedurls option](http://www.rowehl.com/blog/wp-content/uploads/2006/08/http_load-miker-01patch.txt) to select from the url list sequentially (repeating the list once you get to the end) instead of randomly choosing. Reading the whole file in and parsing it probably isn't the way to go for this particular usage, so I'll have to clean it up when the traffic segments I'm playing get into the millions instead of just the tens of thousands. But it works great for now.
