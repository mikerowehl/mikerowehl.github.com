---
date: 2005-03-16 17:36:42
layout: post
title: Some Changes in the Feedster UI - Detect Dominating Sources
---

We pushed out some changes to the front end at Feedster.  For example, take a look at [this search for "slashdot"](http://feedster.com/search.php?hl=en&ie=UTF-8&limit=15&q=slashdot&sort=date). If the results haven't changed by the time you read that, you get a hint on the top of the results page saying that most of the results are from a single source.  Namely slashdot.org. And it gives you some links there to either exclude the site, or list only results from that site. The underlying features necessary to do that have been in there, but now we detect the condition and give some links to do what we think someone would want to do in response.  We've been getting lots of feedback that some searches are dominated by a single source, and in general they're a source that would better be ignored. So here's a way to filter the results easily when that happens. And it's discoverable, not a hidden option that someone has to go looking for, it's right there when you need it most (hopefully). So does that work out well?  Let us know. Are there other conditions we should be picking up?

Tags: [Feedster](http://www.bitsplitter.net/tag.php/feedster)
