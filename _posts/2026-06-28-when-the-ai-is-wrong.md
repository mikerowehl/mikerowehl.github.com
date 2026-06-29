---
layout: post
title: When the AI is Wrong
date: 2026-06-28 20:48 -0700
---
We had an interesting issue at work this past week. One of the developers
flagged a problem that seemed to be network related. They had done all of the
legwork to track it down, had some AI assistance to validate that the most
likely problem was that we had some kind of network blocking in place, tried a
few workarounds, and sent the details over to us when it seemed conclusive that
it was a network issue. But the devops folks double checked locally, ran some
tests from the same container that was having the issue, and everything was
working just fine. It must be an error in the code. Initially the issue was
stuck. Engineers thought it was a problem in infrastructure, infrastructure
thought it was a problem in the code. Both were wrong as it
turns out. It was
[the bug in Node 24.17.0 related to pooled socket reuse](https://github.com/nodejs/node/issues/63989)
Luckily when I spotted the ticket I knew what it was right away. We
were able to get things unblocked and zooming back along pretty quickly.

I didn't think too much about it at the time. While I was out running a few
days later it kept popping back into my head. What should we be doing
when the normal AI debugging path isn't enough? There are lots of people who
would point to this example and claim that it demonstrates shortcomings of the
current AI offerings. And there are lots of AI boosters who would counter that
obviously the problem is that the debugging was done without giving the AI
proper context to figure out the real problem. I think both of those points is
correct to a degree.

As much as I love the idea of teaching an AI how to spot a pattern the way I
do so that my entire organization can benefit from an insight instead of
needing to replicate it, that same thought runs counter to most of what I know
about how technical people actually get better at their role. We tend to learn
more from the things we get wrong than we do from the things we get right. I'm
not saying we should just blindly charge into bad ideas for the sake of
learning. Rather that we shouldn't disregard the value of sometimes working
through the problem without having a pattern handed to us. Even if the problem
we're working on happens to be how to get the right context into an AI.

And you might also be wondering how I "knew what the problem was right away".
I'm not a Node person, I don't tend to be up to date on the latest point
release of every tool, I'm not hooked into the CVE stream in a way that would
have plopped the issue on my radar either. I knew what it was cause I had
been chatting with another engineer a few days earlier and they were griping
about a Node update managing to slip through their blue-green release window
and taking out a bunch of services. Just happened to stick in my head. That's
the other take away. Don't forget the value of just talking to other smart
people. It's hard to know what the value will be, but it almost always shows
up eventually.
