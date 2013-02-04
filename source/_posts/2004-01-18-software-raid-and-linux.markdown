---
comments: true
date: 2004-01-18 10:56:07
layout: post
slug: software-raid-and-linux
title: Software RAID and Linux
wordpress_id: 115
categories:
- Open Source
---

I've been setting up software RAID for the guys at [Zamples](http://www.zamples.com), and I found the [Boot Root RAID Lilo HOWTO](http://www.tldp.org/HOWTO/Boot+Root+Raid+LILO-3.html) to be quite informative. I had never seen that doc before, and it addressed exactly what I was trying to do. I wasn't able to get the second drive booting directly, probably cause it's a 200gig and the geometry reported is all screwy. But at least it appears that it should work if this were a normal configuration. What I've ended up doing is creating a boot floppy to load the system should the primary drive fail. It's not pretty, but until I can dig into LILO and figure out what's up (Yea! I'll have time for that, sure ;-) this is a good enough solution.
