---
date: 2005-01-19 14:25:07
layout: post
title: New Wordpress Install
---

I upgraded my [Wordpress](http://www.wordpress.org) install today. I've been getting a ton of comment spam, and instead of hacking my aging install to deal with it I want to hack a new install. Wordpress has served me really well, and I love the features, so instead of being a punter and just downloading the latest release, I installed the version from CVS instead. Matt said [there are all kinds of antispam things that seem to be working](http://photomatt.net/2005/01/12/no-spam/), so I'll give them a try. And hack if I have issues.

The main problem I have when upgrading is my non-standard template. I do a lot of mobile stuff, and standard site designs are always a pain when viewed from a mobile device. So I always end up stripping things down to a very simple layout that scales from phone to PDA to desktop sizes. Some people don't like the lack of normal interface elements, but in general I think it's what I want. I was going to leave the original template up so that there are two versions of the site, one for people that want to see the standard website elements and my minimalist layout. I discovered that Wordpress now uses templated themes, which did actually make it difficult to just store the original index.php as desktop.php and hack index.php into what I wanted. But I did hack up a [theme called Stark](http://www.bitsplitter.net/projects/stark.tgz) that approximates what I'm going for. There's some user specific info embedded in there now, like links for my email address, Flickr, and Buzznet. So there it is, mas hacking will ensue I think.
