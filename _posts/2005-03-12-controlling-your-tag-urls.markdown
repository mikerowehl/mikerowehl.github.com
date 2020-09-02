---
comments: true
date: 2005-03-12 13:43:43
layout: post
slug: controlling-your-tag-urls
title: Controlling Your Tag URLs
wordpress_id: 445
categories:
- Feedster
---

I haven't finished the test, the tags in my posts don't seem to be getting picked up by Technorati right now for some reason, but I just posted the source to [a simple redirect script](http://www.bitsplitter.net/projects/tag.php.txt) to use when tagging. There's some [concern over linking to Technorati with each tag](http://uncorked.wachob.com/node/38). Technorati knows this, and allows the tag URLs to point anywhere and they still process them. The problem is that then your tag links don't really point anywhere useful. So what about pointing the URLs at yourself? I have that tag.php script sitting on my site so that I can link to something like [http://www.bitsplitter.net/tag.php/entertainment](http://www.bitsplitter.net/tag.php/entertainment). Technorati should pick up the end part of that URL and index the post. But I control the redirect, so that I can change it should I want people clicking on my link to go somewhere else in the future. I also made the tags potentially multileveled, so that I could toss in a link like [http://www.bitsplitter.net/tag.php/photo/106miles](http://www.bitsplitter.net/tag.php/photo/106miles) and it'll go to a [photo page at Flickr](http://www.flickr.com/photos/tags/106miles) instead of [Technorati tag summary page](http://www.technorati.com/tag/106miles). Of course it's a pain in the ass to have to deal with this now, but say [Wordpress](http://www.wordpress.org) eventually grows this function (and eventually other publishing engines, it just starts with Wordpress cause that's what rocks the most). Redirect as a standard function, admin interface to redirect locations, and editing tools that allow tagging posts without having to manually enter HTML - that could be dealable I think. Here's a [link to the basics about Technorati tags](http://www.technorati.com/help/tags.html) for those who have no idea what I'm on about.
