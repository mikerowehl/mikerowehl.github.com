---
comments: true
date: 2005-01-09 03:46:41
layout: post
slug: rss-subscription-service-network
title: RSS Subscription Service Network
wordpress_id: 388
categories:
- Open Source
---

It seems like one of the major complaints that I hear most often about RSS is that it's hard to use. Finding the XML link if there is one, choosing from multiple if there are different options, cutting and pasting the link, knowing where to put it, and dealing with any potential problems. It's just too complex for most people to care about. So publishers attempt to make it easier to subscribe by putting badges on their pages. You know, those little buttons that say "Add to Bloglines" or "Subscribe with NetNewsWire". Unfortunately that puts the burden on the publisher to know all the different services that a user may want to subscribe with, and clutters up the interface with dozens of buttons. A solution like that also increases the barrier to a new aggregator entering into general usage. Publishers won't want to update their site for an aggregator that's only used by a few people, and users won't use an aggregator that doesn't provide them with an easy subscription feature. The interface could be modified a bit, to something like [QuickSub](http://www.methodize.org/quicksub/), to help with the clutter caused by all the extra buttons. But the user still has a boatload of options there, and again creates some friction with respect to adding a new aggregator service. The aggregator provider could do something like create a bookmarklet for easy subscription, but this also has some disadvantages. Such as not normally playing very nicely with [pages that contain more than one feed](http://www.feedster.com/search.php?q=miker+rocks&hl=en&ie=UTF-8&sort=date) and not being available when the browser has restricted functionality (such as on mobile devices). The ideal I think is a service that:







  * Displays just one button, the right button, for subscription via the aggregator the user does their reading with and that's all.


  * Doesn't require publishers to know about the details of every different tool that can be used to subscribe.


  * Allows the author of a new aggregator to service their users directly, without requiring the author of the new software to ask to get their tool listed.





I just hacked together a quick example system that does this to try to get a conversation going. It's based somewhat on the idea of a service network. Somewhat like the way that publishers can include [a bit of code on their site to display ads from a service like AdSense](http://www.google.com/services/adsense_tour/page3.html). Except instead of having the network site display ads we'll ask it to write a subscription button into the page. The publisher site just needs to pass along info about what the feed URL is, and the subscription button service takes care of looking up wich aggregator the user prefers and how to generate the appropriate button for subscription.





The code is very much just proof-of-concept garbage, but I've [put it online](http://www.bitsplitter.net/projects/subservice-0.1.tgz) so that hopefully if people are interested we can get something going. If you can read even just a little bit of PHP and HTML you should be able to follow along with the code from the tarball or walk thru a few pages (starting with the [feed list page](http://www.bitsplitter.net/projects/subservice/test.html)) to see what it does. Here are a few points to call out.







  * The simple javascript inclusion can be wrapped with a noscript tag to create a link to a subscription network page instead. Which means this could also work even for browsers that don't support javascript. It would mean another page to click thru, bit it would still function.


  * Configuration is all held in two cookies, nothing needs to be stored server side.


  * As long as an aggregator author can express subscription to their service as a simple templated URL (containing the feed to subscribe to) they can give their users a link to configure the network to present their tool as the default. Even if the network doesn't know anything about the tool it can still be used. If you're looking at the code, think about passing in an arbitrary template value to setsub.php  A simple "click here to set bloglines as your default aggregator" link could replace the "drag this link to your toolbar to create a bloglines subscription bookmarklet" step.


  * If the user doesn't have any default aggregator set they still see a generic subscribe button, and they can be introduced to the network very quickly if they haven't already used their aggregator to set it as the default.


  * We'll obviously need a lot more hooks and options to let publishers and users control the look of the controls.


  * As long as the tool registers a URL handler it can be used as the target of the network subscription (ie. NetNewsWire and the feed: URL type).





I'm assuming the reason no one seems to have something like this setup is that there's no real direct value in it. It needs to be a single network service in order to be most valuable. We want the user to set their preference once and have it used anywhere there are subscription options. But in general the service needs to be completely invisible. Not a great business, but a valuable service I think. So there's the code example. I think this is something that would really work for the users, publishers, and tools authors. If we can just figure out a way to get it up and running and keep it running. If you agree, and you're interested in trying to make a go of it, let me know.
