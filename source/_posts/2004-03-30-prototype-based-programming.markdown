---
comments: true
date: 2004-03-30 10:17:19
layout: post
slug: prototype-based-programming
title: Prototype Based Programming
wordpress_id: 220
categories:
- Open Source
---

There's been a decent amount of discussion about prototype based programming lately, with two new projects called [Prothon](http://www.prothon.org/) and [Slate](http://slate.tunes.org/) getting most of the press. So all of this gets the question, what the hell is a prototype based programming language? There's a [definition in the Wikipedia](http://en.wikipedia.org/wiki/Prototype_based) which can shed a bit of light on it. The [description of Self](http://research.sun.com/self/papers/self-power.html) from the Self site gets a bit heady, but their explanation of the fundamental nature of message passing and the benefits provided in terms of maintenance are worth the time. If you're looking for a really quick description check out the [Prothon description](http://www.prothon.org/description.htm). Or go searching through the resources for any of the [other prototype based languages](http://www.dekorte.com/Proto/Chart.html).. there seem to be quite a few. Most of them I've never even heard of.

My main question is why is there a sudden surge in interest for these languages? Are people just now coming to see the benefits? I hadn't heard of prototype based objects before, so maybe the concepts just got laid in front of the right people at the right time. Self seems to be a very young system, so maybe the concepts weren't well explored yet. But given the capabilities of the systems, such as being able to change behavior of objects "on the fly" and the ability to include active variables implicitly (see the Self paper for why this is), I'm wondering if the interest stems somewhat from the System Oriented Architecture and Web Services pushes going on. When your business process becomes an always on application of distributed objects you have a strong motivator to search for the ultimate runtime flexibility so you can fix problems with the system still up and running. Just a thought. To me it seems there's a very good match there.
