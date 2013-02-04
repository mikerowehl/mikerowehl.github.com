---
comments: true
date: 2005-05-27 15:47:20
layout: post
slug: odd-quirk-in-bloglines-cache-handling
title: Odd Quirk in Bloglines Cache Handling
wordpress_id: 516
categories:
- Feedster
---

I noticed something kinda odd when adding a new feed to our ad publishing system today. I test with [Bloglines](http://www.bloglines.com) cause I love the system. It's my normal use aggregator and by far my favorite. However I noticed that after having run my testing feeds with ads in them through Bloglines that when I went to view the source version of the feed in Bloglines it had ads in it too!  I went back and viewed the source of the feed in my browser, and sure enough there were no ads.  Hmm, it seems like my testing of the ad populated version somehow caused ads to appear in the original version. How could that be? When I test out feeds I put them in a public place, and just scp the feed output from my laptop and pass it through some web based aggregators to make sure that nothing odd happens. However I don't change any of the links within the feed.  So although my feed might reside at, oh, I don't know, lets say [http://www.bitsplitter.net/herepiggypiggypiggy.xml](http://www.bitsplitter.net/herepiggypiggypiggy.xml), the links within the feed still point to site the original content came from. The end result is that if you have a link like [http://www.bloglines.com/sub/http://www.wingedpig.com/index.rss](http://www.bloglines.com/sub/http://www.wingedpig.com/index.rss) which would seem to subscribe you to Mark Fletcher's blog, it really takes you to a fake post I shoved into Bloglines to make it look kinda like it's hosted at Mark's site. Astute subscribers will notice the mismatch between the urls in the feed info, but most people aren't astute. I think there might be more insidious uses for this, like setting the link location for the feed to an already existing site. I don't want to be mean and try it on existing feeds, but my little bit of fooling around would seem to indicate that the fake version could shove entries into the cache for the overall feed. So there you go Bloglines folks, there's my free suggestion for the day. Refetch if the current cache version comes from outside the link domain and the user is requesting an "authoritative copy" (something from the same URL as the feed link).

Update: Niall [did one too](http://www.bloglines.com/sub/http://www.wingedpig.com/). He helped me test out the stuff I was playing with.
