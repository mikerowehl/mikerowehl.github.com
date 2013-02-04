---
comments: true
date: 2005-03-16 17:09:49
layout: post
slug: the-easier-faster-route-to-building-mobile-applications-using-the-best-of-existing-approaches-and-overcoming-current-limitations
title: 'The Easier, Faster Route to Building Mobile Applications: Using the Best of
  Existing Approaches and Overcoming Current Limitations'
wordpress_id: 461
categories:
- Mobile Computing
---

[The Easier, Faster Route to Building Mobile Applications: Using the Best of Existing Approaches and Overcoming Current Limitations](http://conferences.oreillynet.com/cs/et2005/view/e_sess/6484)

Rodney from [MFoundry](http://www.mfoundry.com/) presented, I know him from [Mobile Monday](http://www.mobilemonday.com).

Typical lifecycle: development -> application testing -> device testing < - > porting

You can optionally also go through certification and signing, and then on to provisioning.

Be prepared to buy phones! for testing by the way, you won't make it anywhere talking to the carrier without running on the actual hardware.

The MFoundry model is Development -> application testing -> provisioning.

Two ways to get things onto phone, which really boil down to one, you download it.  Called OTA (Over The Air) - that just means you download it.

Available applciation technologies (US) - 75% J2ME, 20% BREW, 5% other (PalmOS, .Net CF, SymbianOS)

WAP, it's easy to do, there's a lot of support for it, low cost, flexible, poor user experience. Compare that with applications, which have good graphics , threading, caching, and has a good user interface.  But it's more expensive, there's a lot of training to do, porting, and to update you have to install a new version (compared to an online service, no update needed there).  Applications are for serious developers only, but WAP is a suboptimal solution.

MWorks is the mFoundry approach, best of both.  Development is done in XML and published to the server for download. There's some software running on the phone, MRE (moblet runtime environment). Super tiny, 52k. MIL, moblet instruction language, is all that it understands. 

MRE < -> mWorks Service < -> Content/Databases/Web Services

mWorks Services.  XML is a bloated format, lots of overhead. The primary role of the mWorks services is compression, encoding. If you're interested, W3C, WAP Binary XML is the standard to check out. They call it binary XML in their version, bXML, which gets better compression than the spec version.

They use Eclipse for development, they have a plugin. The other side is the mWorks portal, which isn't that compelling for smaller shops, but for the enterprise it's very interesting.  Portal still is under development, going public in the next month or two.

The current version has full coverage of MIDP 1.0. Everything available through MIDP 1.0 is exposed via the XML language. That means there's a lot that isn't accessable from the phone functions, so this is not the platform for you if you're doing a game. This is good for portals and data applications.

Use ME for SE emulation, a version of ME running on top of Java.

The interface for MFoundry by default looks much more like a "media player" than the default Brew or Java look.  Mostly forms based.

There's an XML parser, by the same people who did MEforSE.

So how do you develop?  It all start with a .mil file.  MIL is a declarative language. Screen description, options (buttons), http service. You can upload an XSL filter to the server to run to compress the information.

So you have information on the device, you want to put it on the screen.  For an imperative language you would use a foreach, in MIL you use XPath. You have a tag called a repeater, that repeats markup for each node that matches an expression.

If anyone is interested in developing, they're offering a beta program for early developers.  All the tools are free.

Tags: [ETech2005](http://www.bitsplitter.net/tag.php/etech2005)
