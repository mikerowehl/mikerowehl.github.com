---
layout: post
title: "Resurrection"
date: 2013-02-04 23:29
comments: true
categories: 
- General
---
This blog has been dormant for a long time, but I've decided to start it back
up. I created the site cause I wanted a Wordpress install
I could test my PalmOS based mobile blogging client against. But once I had
the site
up and running I started tossing all sorts of random stuff in. Everything from
my own thoughts on [scalability](/blog/2006/04/02/high-availability-nfs/)
to summaries of events
about [the FabLab](/blog/2005/04/15/make-almost-anything/).
However, after a few years of tossing all sorts of random stuff in here I
started to really focus on mobile, so I
created a mobile specific site called 
[This is Mobility](http://thisismobility.com/blog) so that I wouldn't have
everything all jumbled together. Then with
so much interesting stuff happening in mobile this blog eventually fell into
disuse. And it's remained unused since 2006.

Recently I've felt getting a little more randomness going again is a good
idea. And I'm really happy I kept all these blog posts around to read,
so I could get a peek back into my mind 10 years ago and remind myself what it
was like. When I started reading through these posts I figured that's all I
would do, read and then put it aside. But I realized how different my
thought process was a few years ago. And not just cause I was young and
naive, but because I was looking at things without the encumbrance of much
bias. "[Beginner's mind](http://en.wikipedia.org/wiki/Shoshin)" is probably
the best term for it. That beginners mind 
decided that Linux and open source were a good bet for building online
services. And that beginners mind decided that homesteading a spot in the
mobile world was a good idea back in 2003. I wouldn't pass on getting a bit
more of that beginners mind, and it seemed like writing
here again could help with that process. With the site also being 10 years
also, it seemed somehow proper to bring it back.

Of course, some updating needed to be done. While I love Wordpress for
some things, I'm also getting tired of it getting exploited and abused cause I
pay so little attention to it. It's my own fault for not updating it, but I
really like the option of swapping to something I don't need to pay attention
to instead of modifying my behavior.  So I swapped over to using
[Octopress](http://octopress.org/),
which
uses post files written in markdown to generate the site as a static set of
pages (hat tip to [Tony](http://fusion94.org/) for the suggestion).
Thanks to a fantastic set of scripts called
[exitwp](https://github.com/thomasf/exitwp) I was able to move
an export of my Wordpress data right into Octopress friendly format.
Yay! That should be the end of Viagra and Levitra ads randomly
appearing at the end of my posts. And as a bonus I can publish the whole thing
through Github Pages, and store the source in Github. Which I was doing with
the rowehl.com site anyway, but had to take special care to backup the
database to keep blog posts safe. Now it's all just one repo. 
And cause the pages are hosted directly off Github, when I crash
my personal server doing Linux distro hackery I don't take down rowehl.com.

Also nice about Octopress - the default profile takes a responsive
approach. So now my personal blog looks better on mobile than my mobile
focused blog. With the way the Octopress templates and plugins are
structured it was pretty easy to make some style changes, swap in some fonts
that make the site look a little less amateur hour. I got rid of commenting
all together and have added some share buttons instead, cause that's how the
world works now. Everyone already has their own place to speak, so why put
their thoughts into my database? And again, once less thing for me to worry
about.

In the end, actually not much effort at all. And I'm really happy with how it
works. Now I have a place to write about all that other
not-specifically-mobile stuff like cool bits of open source, programming,
emerging technologies, and startups. And to remind myself just how far things
have come, I dug up and posted the
[source code](https://github.com/mikerowehl/vagablog) to the Treo650 blogging
app that kicked this whole thing off 10 years ago.
