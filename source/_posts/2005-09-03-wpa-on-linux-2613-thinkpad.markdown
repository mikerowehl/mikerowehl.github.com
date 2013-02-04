---
comments: true
date: 2005-09-03 01:36:19
layout: post
slug: wpa-on-linux-2613-thinkpad
title: WPA on Linux 2.6.13 Thinkpad
wordpress_id: 563
categories:
- Open Source
---

I installed 2.6.13 on my Thinkpad today (it's magically changed from an R51 to an X32, you're not gonna hear me complain). I figured I would follow up on my [initial WPA Linux post](http://www.bitsplitter.net/blog/?p=550) and mention that the Wireless Extensions version 18 are included now, and the ipw2200 driver uses the wireless extensions instead of custom ioctl()s now. Net effect: compile wpa_supplicant with CONFIG_DRIVER_WEXT=y in the .config file, and run wpa_supplicant with -D wext to use the wireless extensions when wpa_supplicant is running. If you don't you get an errors something like "ioctl[IPW_IOCTL_WPA_SUPPLICANT]: Operation not supported" when you run wpa_supplicant. The support seems to be a little rough on this new laptop, it takes a few tries sometimes to attach to the access point, and for some reason I can't get DHCP replies. Though if I keep trying till it connects and then setup the interface by hand it works. I'll have to dig into it at some other point and see what's going wrong.
