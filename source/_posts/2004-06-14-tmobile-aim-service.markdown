---
comments: true
date: 2004-06-14 07:23:04
layout: post
slug: tmobile-aim-service
title: TMobile AIM Service
wordpress_id: 280
categories:
- Mobile Computing
---

I tried to use the TMobile interface for using AOL Instant Messenger from my mobile phone the other day, and it didn't quite work out the way that I had hoped. In the past I probably would have gone off on a rant about it. But now that I have an unlimited data account, and because the AIM interface is a free feature, I'm not going to do that. Instead I'm going to say that it's pretty cool of TMobile to try to integrate their online services with existing offerings. They just have some work to do before the service is generally applicable. There are a few quirks and limitations that make the service hard to use and impractical if the people you're talking to don't know to modify their behavior to account for the interface you're using.

The first issue is the most grievous offense actually. Once you sign on to the service it notifies you of new messages via WAP push. This is actually pretty crappy of them, because push messages are NOT a limitless resource, at least I don't think so. I won't rant about that right now, cause first I want to validate this suspicion about the cost. However, even without the cost factor, this was really annoying and a hindrance to using the service. There was no way to turn off these messages that I was able to find. And each time a new message came it interferes with whatever you're doing. You have to acknowledge the message in an asynchronous pop-up screen. This really sucked when the person I was talking to wrote a bunch of really short messages like:

Hey, you there?
I have a meeting soon.
I have to go now.
See you soon.

Which generated 4 separate messages that came in right on top of each other, and were disruptive enough that I couldn't get a response in at all before it was too late. Why the WAP pushes? [WINKsite](http://winksite.com/) does its group chat using an automatically refreshed page. That's really worked out well on just about every device I've tried it from.

The conversations page also seems to only display new messages when you load it. That means that if you're reading messages from a conversation, and you accept a WAP push of a new message, the page you end up at no longer holds the text you were just reading. That sucks IMO. If you want to draw attention to newest messages then reverse the order in which the messages are displayed (newest messages at the top) and maybe put a marker next to the new lines. Displaying only the new messages takes all of the context out of what should be a nice flow of conversation. That gets confusing enough when you have a single conversation that keeps you bouncing back and forth between WAP push notification screens and the browser. It's almost impossible if you have multiple conversations going on.

The last one might have been user error, but it was user error caused by multiple issues with the features as implemented. It seems like the scrollback buffer is only a few lines long. When I logged in at one point I started a conversation with my girlfriend. I said hello, and that I was on the train on my way back from a meeting. This triggered a torrent of messages. Not at all out of the realm of normal use. The reason for using IM is to keep in touch, right? And she had some news. So she wrote a message and I got the push, which I accepted. While I'm waiting for the browser to load, I get another message. Bing, bing bing bing. This goes on for maybe a half dozen messages, I lost count. Finally I have a browser sitting in front of me with what are obviously messages from the middle of a long story she's telling. I don't have the start of the story, and the WAP messages are binging in so quickly that I can't get a message back to her to say that I missed the start of her story. That really sucked.

So, the obvious programmer answer to this is to just not talk to people who send torrents of messages like that. But I would really like to see mobile services reach mass appeal. And while TMobile has made a good effort in terms of providing a service to make the mobile experience more continuous with the online experience, it doesn't quite make it to the level it needs for general usage. It just isn't realistic to expect every user to work out some way to let the people that they talk to know that they're on a mobile phone when they login. And if the service really is supposed to unify desktop and mobile messaging it needs to enable the same operations or provide some mechanism for dealing with the differences easily (hopefully automatically). Some of the issues seem to just require minor tweaks. Keep old messages on the conversation screen, reverse the display order so that the newest messages are at the top, and provide a config option to disable WAP push and make the conversations page automatically update.
