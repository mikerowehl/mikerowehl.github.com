---
comments: true
date: 2004-12-29 23:04:42
layout: post
slug: html-browser-bookmarks-to-rss-populated-opml
title: HTML Browser Bookmarks to RSS Populated OPML?
wordpress_id: 380
categories:
- Feedster
---

Fooling around a bit with the [Feedster feed info API](http://www.bitsplitter.net/blog/index.php?p=377) I was looking for a way to export Firefox bookmarks as OPML and then use the feed info API to fill in the feeds associated with bookmarked web pages. There's [a bookmark extension](http://syncmarks.mozdev.org/) which apparently will output in XBEL. But in my opinion even just asking users to install an extension is too much. People should be able to export their bookmarks from the stock tool and upload the file to an aggie or online service to bootstrap their subscriptions. From what I've seen this is where the standard users are living right now. Some are using portal services, but not all. And those who are using portals normally have some info they still read outside of the portal. They have their favorites bookmarked, and they run through their bookmarks reading news. We can figure out if there are feeds associated with the pages they have tagged, there should be an automatic process for this. Sorting through sites and looking for XML buttons and cutting and pasting URLs is a pain in the ass, and that assumes a level of knowledge that I'm not seeing in the non-geek crowd I've been chatting with lately. Anyone know of tools or services that do the conversion?
