---
layout: post
title: Builder Research - Basic Attention Token
date: 2025-11-06 15:47 -0800
---

I've recently started getting back into some blockchain development. A part of
that has been digging into some projects to figure out where I might be able
to help out, and just sharpening up my analysis when it comes to crypto
projects. A vast majority of the info you find on the crypto sites is focused
on the value of a token. I want to know what the state of a project is from
the builder perspective though. Is this something I can build around or on top
of to help create some value?

The [Basic Attention Token](https://basicattentiontoken.org/) is a pretty OG
project. I suspect most of the folks who are interested in the project already
know the broad strokes of what it was meant to do. But in case you somehow
landed on this and you don't already know about BAT, the super high level
overview is that the token was meant to bring to the forefront the value
exchange around attention that happens during advertising. Many of us don't
think about it, but when it comes to a lot of the business on the internet, we
the users are the "product" that gets sold. It's our attention (and the
potential to divert that attention into commerce) that really drives most of
the sites we use and think of as "free". We normally aren't aware of the big
machine that's trying to process our attention into dollars for someone else
because it's often intentionally hidden. And even when it isn't hidden there
are often so many stakeholders involved in what's going on that it can be hard
to unwind who is doing what and what data is involved. The Basic Attention 
Token was meant to simplify and make the value exchange explicit.

That was the high level pitch as it had existed a few years ago. And
admittedly I haven't followed it closely in the time since. I've tried to
bring myself up to speed over the last month or so, and there might be some
things I've missed in trying to figure out the current situation. But I'm
pretty sure I've got the major parts right, at least as far as thinking about
the token as a component of a development plan. The TL;DR is
that the token itself seems to be in transition as Brave transfers to a
different vision of how crypto and blockchain should fit into their overall
strategy. If you're interested in more detail than that I'll try to lay it
out.

The flow of BAT through the system is supposed to mainly be in
support of creators. The central diagram on the BAT site shows a flow of BAT
from both advertisers and users to creators. And the logo itself is
[meant to represent the relationship between advertisers, users, and creators](https://www.reddit.com/r/BATProject/comments/n1yasp/what_does_the_bat_logo_represent/)
in the system they're trying to create. But it seems like that relationship
has broken down under the current system.

In the original whitepaper the compensation paid out to the creators was meant
to
be an automatic outflow. The browsers would use directly instrumented time on
property to figure out how much BAT should be directed to the publisher of a
piece of content, and it would happen automatically behind the scenes. This was
dropped as an option a while ago. I'm
certainly not going to fault them for this no longer being the system in use
currently. I could see there being some huge issues with this method of
distribution.

In the absence of the automated contribution I did expect there to be a
effective alternative. I pictured there being decent tools for supporting
creators - maybe some tools for creators to drive the process on their own.
In my mind that would be things like setting up ongoing contributions to your
favorite creators, maybe tools for token gating some content, options to setup
automatic BAT splits between multiple creators working on a collaboration.
When I was looking at this part of the market a few years ago that's the kind
of stuff the crypto-forward creators were looking at. But so far I haven't
really seen evidence of activity on the publisher side. I've had a really
hard time trying to size the outflow of payments to creators at all. There are
lots of numbers shared on the BAT site, but amount of BAT paid out to creators
isn't one of the metrics. I would consider that core if the overall plan today
is the same as it was originally.

So I just did some legwork. I figured of all the folks likely to have BAT
contributions enabled, the blockchain and crypto media should skew higher
usage. And
since their audience is other crypto enthusiasts I assumed they would get 
some contributions. Figuring out how much usage there is for direct
contribution is admittedly kinda hard. The BAT token was on the Ethereum chain
to begin with, but it got bridged over to Solana to keep the costs down. That
makes sense. And there are a bunch of custodial systems that were built into
the Brave wallet to make it easy to sign up for the system and get users and
creators onboarded. But what I was surprised to see was that the existing
mechanisms didn't smooth over the differences. I would often find someone who
did have contributions enabled, but when I went to contribute to them I wasn't
able to because they're on Uphold. That's just broken. You have a user with
BAT in the wallet you told them to setup, and a creator who's asking for BAT
to support their efforts, but it's not possible to complete the transaction?
If that main loop in the system isn't working consistently it was hard for me
to picture that the overall health was great.

The wallet I have setup on Brave is a direct Ethereum account though, so the
few times I was able to get someone who was signed up as a Brave Creator and
also had the right config on their side I was able to send them some Eth. And
of course I could see the account I was sending to for those donations. There
had been some other technologies in the mix at one point to keep users
anonymous, but in this version at least we're able to see each other for Eth
donations. My system is obviously not scientific at all, but I just wanted to
get something of a feel for if publishers were getting paid out at all. And
from what I've been able to see, no. The few accounts I was able to get a bit
of a view into had very low activity. In one case, before my donation the last
deposit had been almost three years ago. And that was a pretty decent account
with a lot of activity that I would have expected to be a highlight.

But the BAT token itself is doing pretty well in terms of price, so what does
it really matter if the publishers aren't ending up with the token? That
happens because the Brave Rewards system has the token as part of the process.
So advertisers on Brave need the token to be able to reward users, that puts
the token in a pretty decent place compared to lots of others that don't have
any utility at all associated with them. That's great for the price of the 
token, but not so much for the health of the ecosystem. For example, one of
the big selling points of Brave is that it does a lot of ad blocking and
stripping unessential content by default. (It really is a great browser by the
way. It's my daily driver browser and they're doing great work over there, I 
just don't think the BAT token is working). If your browser is stripping out
ads that normally makes the content creators somewhat upset, cause they don't
get paid for the views of their content. If you have an alternative way
for them to get compensated there's a great answer to the content creators
concerns. But if you're both blocking ads and not really minding how the new
system could be funneling them alternative value, there could be some issues
down the line.

And there are some other efforts that seem a bit odd in relation to the core
flow. Brave was encouraging a memecoin called Guano that
rewarded folks for locking up their BAT. And they've made a partnership to
allow for registering a .brave domain using your BAT. These things aren't 
necessarily bad, but they don't seem to be in service to the core mechanism
the token is supposed to support. The cynical side of me would say they seem
like the kind of thing I would do if I needed to
increase velocity of the token and provide some utility exits for BAT that was
pooling with users. But instead I'll just say that these alternative ways to
use BAT just further starve out the creators. There are a few posts on the
community forum from creators who had been making some BAT for a while and
have seem a pretty drastic drop-off recently. I wouldn't be surprised if that
drop-off correlated with the Guano launch. Why would users donate if they can
earn from their locked up BAT? Especially when actually using the BAT to
donate doesn't even work a lot of the time?

So that's my long winded version. Brave is open source by the way, the
community seems to be pretty accepting. My hope had been that I would find
something useful I could do to help out for the project. I know it's not all
on Brave to solve every problem on their own. However, with the core loop of
the currency looking like it has stalled, I don't think it makes
sense to try to build with it. It seems like the roll of the token now
is shifting to a new model. When I see the things like their domain 
registration partnership and native IPFS support I think maybe there's another
story starting to emerge around evening out access to infrastructure for folks
underserved by existing providers. There's been mention on the community calls
of a revised roadmap coming up, hopefully that clears some of this up. I'll
cycle back around to it when there are some updates.
