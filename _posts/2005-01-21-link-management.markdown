---
comments: true
date: 2005-01-21 13:31:15
layout: post
slug: link-management
title: Link Management
wordpress_id: 397
categories:
- General
---

I ran into [Tantek](http://tantek.com/log/) last night at [Russ's birthday party](http://www.russellbeattie.com/notebook/1008256.html), and talking with him reminded me that I never updated my blog to include [XFN info](http://gmpg.org/xfn/). [Wordpress](http://www.wordpress.org) includes a nice simple XFN generator for the links section, so I decided to use that. I had originally populated the links with an import of the OPML from Bloglines, so adding the relationship info was a snap. Then I started thinking about keeping the info up to date, and synced in the different places it needs to live. Since Wordpress manages the XFN info for me, and publishes it, I figured using Wordpress as the authoritative source would be a good idea.





The two major places that I want my info are here on my blog and in [Bloglines](http://www.bloglines.com), the web based aggregator I use. I figured it would be pretty easy to get Bloglines to sync with Wordpress in a repeatable manner, but not quite. First I figured I would just be able to look at some URLs and create a bookmarklet in [FireFox](http://www.mozilla.org/products/firefox/) to import the OPML into bloglines based on the [OPML export](http://www.bitsplitter.net/blog/wp-links-opml.php) that Wordpress does. But it turns out that Bloglines wants the OPML uploaded as a file. Not a big deal, but I'm surprised they don't take a URL for that import field. After fooling around a bit to make sure that multiple import will work the way I expect I ran into two issues:






  * Bloglines treats the first category it hits as the base folder, so one category of feeds was getting dumped into the root instead of their own location. I just created a dummy category in Wordpress to appear as the first category in the OPML and I ignore it.


  * Every time I import the folders get duplicated. The new copy is empty, so they're easy to delete out, and it doesn't mess with the status of the feeds or anything. But it's annoying. This was a real pain, I want my links to just sync between the services.




So I have a simple, [effectively three line perl script](http://www.bitsplitter.net/projects/wp-to-bloglines.txt) that I should be able to just throw in cron to sync my feeds, but instead I have to run it by hand. The goal would be a bookmarklet that adds the current page into my Wordpress links so that I can add XFN info, and somewhere in the background have something sync the feed for my new friend over to Bloglines. I don't know if that reimport problem with Bloglines is a well known issue or not, but I submitted a note to see what they say. If that was working well it would be a cool feature to add syncing with Bloglines directly into Wordpress. I could just parse the Javascript to figure out the structure of the folders and delete out the dupes, but that just smacks of effort.
