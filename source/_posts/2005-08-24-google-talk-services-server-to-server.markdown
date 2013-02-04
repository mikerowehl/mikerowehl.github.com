---
comments: true
date: 2005-08-24 21:11:39
layout: post
slug: google-talk-services-server-to-server
title: 'Google Talk: Services? Server to Server?'
wordpress_id: 549
categories:
- General
---

Okay, not that I have the time to play with something new, but I had to get this out of my system cause I haven't seen other comments yet (Well, except [this one](http://www.decaffeinated.org/archives/2005/08/25/googletalk)). One of the reasons I got really jazzed about [Google Talk](http://talk.google.com) running XMPP underneath is because XMPP is a more distributed protocol than the IM systems. What I mean by that is that there's supposed to be server to server communication. Even though I run my own Jabber server at bitsplitter.net I can still talk to folks at jabber.org because the servers figure out how to talk. Kinda like the way email gets from one place to another. When the jabber.org server sees thatguymike@bitsplitter.net, jabber.org knows to open a connection to bitsplitter.net and start delivering messages. So not only can you create plugins to Jabber by creating things that emulate clients, you can toss a whole server into the mix. And all the other servers can communicate with it by default cause the domain based naming scheme for Jabber accounts takes care of telling the server how to find each other. Sweet.  Except this doesn't seem to be true for talk.google.com. My username is "miker@gmail.com" but the service to connect to is at talk.google.com. Hmm.  Maybe miker@gmail.com@talk.google.com works? Doesn't seem like it. Maybe from the Google Talk side I can add my bitsplitter.net account? No go, looks like the Google Talk folks have server to server communication off. That sucks. Turn it on!

Also, here's an idea I would like to try, but I don't have time for. Maybe if you do you can. I can't get any of the normal dedicated Jabber clients to talk to Google Talk ([Gossip](http://developer.imendio.com/wiki/Gossip) or [Gabber](http://gabber.sourceforge.net/) for example). Why would it matter? Because Jabber also supports something called services. These are server side goodies to keep all sorts of neat info or provide extension functions. Examples: directories of users on the system, info about the group chat rooms, or gateways into other protocols or sources of information. What's installed on that Google Talk server?  What services are there? Without allowing server to server communication the extensibility of the platform is really in question. Dumb. But maybe there are some other goodies in there for now.
