---
comments: true
date: 2005-08-06 13:23:07
layout: post
slug: suse-package-management-and-firefox
title: Suse Package Management and Firefox
wordpress_id: 537
categories:
- Open Source
---

I'm pretty sure there's something about Suse and Yast that I'm supposed to like. Maybe once I get to know it more I will like it. But I have a 64 bit desktop system I'm using now, running Suse Enterprise 9.2, and I have absolutely no idea where to look for packages that don't show up when I search in the Yast tool. Fortunately it's a nice beefy system, so I was able to compile Firefox and Thunderbird and a bunch of other tools when I wasn't able to find packaged versions. But I've run into a bunch of annoying incompatabilities. Take [Spellbound](http://spellbound.sourceforge.net) for example. I love Spellbound, I can't spell at all. I use 'a' where I should use 'e', I love to use 'z' where it's completely inappropriate, and 'i' comes before 'e' about 50% of the time depending on my mood. But I can't get Spellbound to work with my local compile of Firefox. Why?  Ummm... I have no idea. Every time I install it everything seems to go fine. But when I restart it tells me it can't load the extension, I need to reinstall. Is it cause the core of FF is compiled for x86_64 and the spellcheck libs it installs are for 32 bit? I replaced the libs and xpi from the packaged spelling library with the versions from my Thunderbird compile (which does spell checking fine, W00T!), but that certainly didn't fix it at all. Running firefox from the command line and looking for errors didn't help at all either, nothing there that gave me any hints. So I'm kinda sad. But mostly I feel sorry for you folks, who have to now deal with reading something rife with spelling errors.
