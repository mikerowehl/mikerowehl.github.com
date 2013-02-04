---
comments: true
date: 2005-09-07 12:41:27
layout: post
slug: sound-with-linux-2613-on-thinkpad-x32
title: Sound with Linux 2.6.13 on Thinkpad X32
wordpress_id: 569
categories:
- Open Source
---

I had a problem with the X32 running Linux 2.6.13 where the audio device was there, but I couldn't always hear the output.  I found [this post mentioning that the headphone sensor and line jack sensor both need to be muted](http://www.ussg.iu.edu/hypermail/linux/kernel/0502.2/0755.html), which worked for me. Here's the card info from the model I have:



`miker@spark:~$ cat /proc/asound/cards
0 [I82801DBICH4   ]: ICH4 - Intel 82801DB-ICH4
                     Intel 82801DB-ICH4 with AD1981B at 0xc0000c00, irq 11
miker@spark:~$`



I'm using the alsa driver snd_intel8x0 and made the change using the alsamixer curses tool (although apparently you can turn on the sensor switches for the volume panel control under Gnome as well).
