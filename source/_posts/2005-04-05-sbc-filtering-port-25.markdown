---
comments: true
date: 2005-04-05 22:37:49
layout: post
slug: sbc-filtering-port-25
title: SBC Filtering Port 25
wordpress_id: 482
categories:
- General
---

When Elle and I got home from New Orleans our phone wasn't working and our DSL connection was bouncing up and down. They got that fixed up during the day, thanks to some poking and prodding from Elle.  But this evening when I went to send email I kept getting errors. Fire up netcat, no response at all from the mail server on port 25.  My first reaction is that it must be either network problems or [Dreamhost](http://www.dreamhost.com) bouncing servers (they seem to like to do that).  A while later and I'm still getting errors though. So just for the hell of it I connect up over GPRS and try to send the message like that. Works no problem. Interesting. Sure enough there are random reports scattered all over the place about SBC turning on outbound port filtering for SMTP. Motherfuckers!





[Elle](http://www.ellementk.com) says she's been having trouble with SMTP outbound for a while, and that she saw the suggestion to switch to port 587 somewhere. Sure enough, that works. Turns out port 587 is reserved for the [message submission protocol](http://www.ietf.org/rfc/rfc2476.txt). A protocol that seems to exist entirely as existing description of what should be done with SMTP when using it to insert messages into a system from a client program. I know I sent email from home right before we left for New Orleans, so this must be some on again off again kind of SBC experiment. I'm pretty pissed about it though. Spam sucks, sure. But so do unnotified infrastructure changes. And now my ISP has decided to inconvenience me for their own benefit. Speaking as a customer I can say that this definitely does not increase my satisfaction. I know all the reasons an ISP would block outbound SMTP (they apparently have a spammer problem and must be getting dropped into blocking lists, so they want to route everyone through their own authenticated relay). I just don't think they're valid. It's the cheapest, easiest, bluntest way they could deal with the issue. And this is just them being cheap because they can get away with it, because most people don't understand the underlying issues and what the potential solutions are. It's not like this is a new issue, Lessig wrote about it a long time ago in [The Spam Wars](http://www.lessig.org/content/standard/0,1902,3006,00.html):





> Certainly, spam is an issue. But the real problem is that vigilantes and network service providers are deciding fundamental policy questions about how the Net will work - each group from its own perspective.

This is policy-making by the "invisible hand." It's not that policy is not being made, but that those making the policy are unaccountable. The self-righteous spam police may or may not be right about the solution to spam; that's not the point....





I pay my ISP to shift packets around, that's all I want it to do.  I apply spam filters on my own, because I know that applying port filtering is about as effective in stopping spam as virgin sacrifice (so folks as SBC, sorry to spoil your fun, but that won't work either). I do not pay them to tell me to what sites and services I'm allowed to connect. But they've decided to take it upon themselves to fill that role. From where I'm standing, they've just decided to partially stop servicing my needs. And with no upside. Don't forget, I don't give a shit if their servers end up blacklisted. This discussion started with me wanting to connect to an external server, which is itself not blacklisted. I do not want them doing this for me, but as far as I know I have no choice. When customer support starts answering their phones again maybe I'll try to find out.
