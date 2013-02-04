---
comments: true
date: 2004-07-27 10:00:29
layout: post
slug: http-delta
title: HTTP Delta
wordpress_id: 323
categories:
- General
---

Jeremy Zawodny has a [post about RSS scaling problems](http://jeremy.zawodny.com/blog/archives/002277.html). Something that came up as a partial solution at one of the blogger meetups was [the HTTP delta proposal](http://www.ietf.org/internet-drafts/draft-mogul-http-delta-10.txt). It's specifically meant to address this issues:




> Many HTTP (Hypertext Transport Protocol) requests cause the retrieval of slightly modified instances of resources for which the client already has a cache entry.




From what I understand there isn't an implementation of this proposal out in the wild. It seems like it would have applicability in more and more places however, so maybe it's about time. This just addresses the bandwidth efficiency however, which is NOT currently most of the concern. Bandwidth is relatively cheap. There's also scalability in terms of computing power required on the server dishing out the RSS. And requiring the server to calculate the differences between the last version that a client has and the current version might eat up more in processing power than it saves in bandwidth. Right now I'm off into the area of wild speculation however, so don't trust what you read here. What I'm really saying is that here's a potential scaling answer. And who knows, if implemented properly on the server side perhaps it could solve both bandwidth and processor cycles.



