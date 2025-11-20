---
layout: post
title: Builder Research - XMTP
date: 2025-11-19 20:16 -0800
---
I ran across [XMTP](https://xmtp.org/) a few times while I was poking around
with other services. But I had pushed it off till later. It wasn't core to
what I was looking at. But then while I was playing around with Paragraph I
saw somewhere XMTP delivery was an option for people to subscribe to your
content. That was a pretty interesting use case, so I picked it up and tried
to experiment with what I could. Keep in mind that my use case is a bit tilted
toward that notification channel idea.

One of the best places I found to get an overview is the 
[Messari research report](https://messari.io/report/xmtp-unifying-web3-communication).
As of right now (Nov 2025) that report has started to get a bit stale, but it
was a great way to understand what some of the high level ideas where. There's
a bunch of pretty marketing heavy copy on the main XMTP site. The use cases and
tools described on the project pages didn't really match up to what I was
seeing in the repos and code. And I never was able to figure out how to get
Paragraph to send anything via XMTP.

I think this stuff is just the result of the project cycling at a pretty high
frequency and working on new things. That did make it necessary to separate
hype and froth from actual service though. When I saw
[the mini apps](https://xmtp.org/miniapps) example showing Base and Farcaster
on top of the Paragraph stuff I had run across initially I thought the project
was up and running in full. I thought maybe I could get involved in some way,
even though I might be late to the party. I'm not sure that's the case though.
I'm pretty sure everything is running on the testnet currently. If there is a
mainnet up and going now I think it might just be getting used for some of the
demo use cases. There is a
[mainnet ops epic](https://github.com/xmtp/xmtpd/issues/1148)
on the project board, but I didn't see any
info about it in the docs. I figured maybe the mainnet stuff was tucked away
behind actually funding an account, but my attempt to check out the funding
portal all ran into errors or permission requests. So I assume that's all very
early stage. Which is all fine, it's an early project.

Like when I had poked around with the
[Basic Attention Token](/2025/11/06/builder-research-basic-attention-token.html)
initially, I just wanted to know if this was something I could just pick up
and build with. I don't think it would be for most of the uses I have in mind
currently. Though I could certainly build something with it. I put the agents
together to demo a simple
[notification setup](https://github.com/mikerowehl/xmtp-notification), and it
works. In order to be useful as a notification system there has to be a
critical mass of people who drive their actions out of the inbox you're
delivering to. I'm not seeing that be the case. That's mostly because
of the target audience and not the technology. I'm currently thinking about some
crypto tools for online content creators. Generally content creators
want to lean on
things that are already mass behaviors, not drive new adoption. I could be
wrong there however. I could certainly see delivering a message about new
content into the same wallet you use to pay for that content yielding better
conversion rates for the content creator. But I assume if that was always the
case the XMTP options in Paragraph would be more prominent.

I do love the idea of the project. I like the idea of interoperability by
keeping the identity and inbox distinct. And messaging of some sort is a core
service, even if we might have to figure out the higher value versions if
there is postage in the system. I'll likely keep poking around. Hopefully I
can find a small area where I can contribute a bit while keeping an eye on
how it evolves.
