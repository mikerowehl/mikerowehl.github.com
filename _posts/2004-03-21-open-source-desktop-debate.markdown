---
date: 2004-03-21 15:29:26
layout: post
title: Open Source Desktop Debate
---

There's [an interesting debate](http://planet.gnome.org/) going on within the [GNOME](http://www.gnome.org) and [Mono](http://www.go-mono.com) communities. The main thread is a debate between [Havoc Pennington](http://log.ometer.com/) and [Miguel de Icaza](http://primates.ximian.com/~miguel/activity-log.php). Lots of other people have contributed to the conversation, but here's a list of some of the main posts (I may have missed some messages in here, but hopefully this will give a decent flow):




  * [http://ometer.com/desktop-language.html](http://ometer.com/desktop-language.html)


  * [http://www.advogato.org/person/lupus/diary.html?start=10](http://www.advogato.org/person/lupus/diary.html?start=10)


  * [http://log.ometer.com/2004-03.html#19](http://log.ometer.com/2004-03.html#19)


  * [http://www.advogato.org/person/lupus/diary.html?start=11](http://www.advogato.org/person/lupus/diary.html?start=11)


  * [http://log.ometer.com/2004-03.html#21.3](http://log.ometer.com/2004-03.html#21.3)


  * [http://log.ometer.com/2004-03.html#21.5](http://log.ometer.com/2004-03.html#21.5)


  * [http://primates.ximian.com/~miguel/archive/2004/Mar-21.html](http://primates.ximian.com/~miguel/archive/2004/Mar-21.html)


  * [http://log.ometer.com/2004-03.html#21.2](http://log.ometer.com/2004-03.html#21.2)


This is essentially a debate about how to go forward with development of an open source desktop system, in particular what technologies and languages to use in implementing the system itself. I think it's interesting to see all the issues that go into making a decision such as this, as of course there are both technical and nontechnical factors.

For those not familiar with [Mono](http://www.go-mono.com/), I would suggest at least skimming the [FAQ](http://www.go-mono.com/faq.html). Compatibility with the .NET system appears to have heavily influenced much of the discussion so far. The planned operating system Longhorn (a Microsoft product) apparently exposes .NET interfaces and plugin APIs at many different levels of the OS. It's an excellent idea for a desktop system, but it's also not a new idea. Why start playing catchup on this concept because Microsoft has decided to implement it? If we want a pluggable desktop system which exposes all user information as objects I would personally opt for building one without waiting to see what Microsoft has done. Compatibility with Longhorn is important, but that doesn't mean that the only way to get advanced desktop features is by waiting to copy a commercial product. I really hope it's not the only way at least. But with the US patent system in the state that it's in, maybe that is the only viable option.
