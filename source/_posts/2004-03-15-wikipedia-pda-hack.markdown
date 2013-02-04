---
comments: true
date: 2004-03-15 00:14:21
layout: post
slug: wikipedia-pda-hack
title: Wikipedia PDA Hack
wordpress_id: 188
categories:
- Mobile Computing
---

The [Wikipedia](http://en.wikipedia.org/wiki/Main_Page) is one hell of a badass project. Great information, technically well done, up to date - it's got everything that most people would ask for. Unfortunately for me, I have some oddball requirements. Such as wanting the Wikipedia to display well on my Clie. There do seem to be some [Palm specific](http://sourceforge.net/tracker/index.php?func=detail&aid=793969&group_id=34373&atid=411195) and [general PDA](http://sourceforge.net/tracker/index.php?func=detail&aid=866314&group_id=34373&atid=411195) related feature requests in the SourceForge tracker for the project. But I'm sure the Wikipedia developers have enough to do already without catering to the ultra-dweebie .001% of the computer using population who would be interested in accessing the site from a handheld device. So in the meantime I created the [Wikipedia PDA hack](http://www.bitsplitter.net/projects/pda_wikipedia.cgi). It's just a few lines of perl which make it easy to jump from one printable view of a page to another. It's not perfect, there are some pages it doesn't pick up (for some reason some nodes direct to the edit view of the page). And it explicitly redirects to the English site. If you find these bugs just too terrible to deal with, you can always just grab [the source](http://www.bitsplitter.net/projects/pda_wikipedia.txt) and fix them. 
