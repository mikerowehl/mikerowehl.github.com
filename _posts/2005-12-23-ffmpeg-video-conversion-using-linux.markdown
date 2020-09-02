---
date: 2005-12-23 00:49:22
layout: post
title: ffmpeg Video Conversion Using Linux
---

I fooled around with [ffmpeg](http://ffmpeg.sourceforge.net/index.php) for a while trying to convert a few videos for use on my iPod Video, and managed to get something working after using [using this description of video conversion](http://www.julien-oster.de/pov/pmcms/entry/122). While the music download and video download were better than expected, this part is what one could call "unpolished".  I ended up needing to use the ffmpeg out of CVS, compiled locally against local compiled versions of [libfaac](http://www.audiocoding.com/modules/mydownloads/) and [xvid](http://www.xvid.org/). The important thing is, I got videos converted. Here's the command line I used:



`ffmpeg -i the_scene_xvid_episode_1.avi -f mov -b 1800 -maxrate 2500 -vcodec xvid -qmin 3 -qmax 5 -s 320x240 -acodec aac -ab 128 ~/the_scene_1.m4v`



I found a few other descriptions, but they had left out the mov format specification (-f mov). All the videos I tried like that just kicked right back to the menu when I tried to play them on the iPod. I haven't verified all the options to make sure that it's really the -f mov that makes the difference, but I'm definite that line above works for me. Maybe it'll help someone else.
