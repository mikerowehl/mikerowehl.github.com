---
date: 2004-01-06 00:00:32
layout: post
title: Kannel Open Source WAP/SMS Gateway
---

I was wandering around looking for info about why it is that my old Palm m515 doesn't work with some WAP sites, and I ran across [Kannel](http://www.kannel.org/), an open source WAP and SMS gateway. I still haven't figured out what the hell the deal is with the Palm, but at least now I can pass requests through a local gateway rather than just having to rely on sniffing the requests sent to the gateway. This is one of the many annoyances of WAP, one that I had forgotten about. Your request has to go out to some third party on the Internet, who then passes the request along to the person who actually fulfills it. Not a big deal, proxies exist all over the place, right? Well, what if you're a developer, and you suspect that the gateway you're sending the request through is mangling it for some reason? Unless you're running the service that you're accessing as well, you normally can't see that. But with Kannel, I can. So here's throwing some props their way. I was able to download the package, compile, setup the wap gateway, and pass requests around. I still have lots of debugging to do, but at least now I can do it. Schweet.
