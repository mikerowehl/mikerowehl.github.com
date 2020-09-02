---
date: 2005-02-03 18:49:19
layout: post
title: USM Under Firefox/Linux
---

[Randy](http://www.kbcafe.com/) seems to have some momentum going for his [Universal Subscription Mechanism](http://www.kbcafe.com/rss/usm.html) proposal. The basic idea is that we deal with some content types specific to RSS and Atom so that the browser can shove the handling off to an external app that then push the subscribe URL into something that knows what to do with it. Not a bad idea, but I like [my idea for a subscription service](http://www.bitsplitter.net/blog/?p=388) better. However, if people think that the proposal Randy made is the way to go I don't want to be a bad sport. I just want things to be simple and work by default. So I hacked together a [Python USM handler](http://www.bitsplitter.net/projects/usm.txt) that works for me under Linux using [Firefox](http://www.firefox.com/). I'm on the train right now, and testing it out against a lot of feeds is a pain over this GPRS connection, so I just tried a few. Using it should be pretty simple. Right now it only handles launching a browser with the [Bloglines](http://www.bloglines.com) subscribe URL, but the hackers out there can change that if they want I'm sure. I'll make it config file driven with some command line options to set the subscription action at some point.

What I would like to do with this is have it pull both the HTML URL and subscription URL and shove that off into my Wordpress link manager "add link" function. Maybe that'll be the next set of hacking, depending how many blogs I happen across that support USM. Mine doesn't :-)  Guess I need the latest latest version of [Wordpress](http://www.wordpress.org).

Update: I messed up the [link to the code](http://www.bitsplitter.net/projects/usm.txt) before. Ooops. I probably can't blame that on the bouncing of the train, but I'm going to try anyway.

Tags: [USM](http://technorati.com/tag/usm) [RSS](http://technorati.com/tag/rss) [Firefox](http://technorati.com/tag/firefox) [python](http://technorati.com/tag/python)
