---
layout: post
title: Modern RSS Usage
date: 2026-01-05 09:09 -0800
---
There used to be a lot of attention and development focused on RSS, a format
meant to make it easy for users to subscribe to updates from a site and merge
multiple subscriptions into a personal news site. There were all kinds of 
homepage creators and news readers that ingested RSS, additional formats for
sharing your set of subscriptions or even how much you read and how much time
you spent on the different sources, and I had worked at one point on a search
engine specifically indexing feed content called Feedster. But as the
centralized networks like Twitter, YouTube, and Facebook gained popularity it
was easier for them to just provide a lot of the capabilities that people were
looking for. So instead of publishing on their own and using RSS to stitch
things together, more and more people just started and stayed on the
platforms. Most people describe this as the centralized platforms having "won"
over RSS. That's true from a lot of different angles. But because RSS is an
open format it isn't true from one very important angle. RSS didn't go away.
It's still available and supported on many platforms. Sometimes even on the
platforms that we think of as having run it over.

I'm unhappy with the way YouTube weights what shows up on my main page. I've
subscribed to lots of channels I actually care about. I might not watch every
video they put out, but I do care about what they post. If they post a few
videos about things I either happen to not care much about, or maybe I already
know a ton about so I don't want to watch more, the algorithm decides I don't
want to watch them any more. They disappear. Instead I get lots of
increasingly crappy videos. Shorts that are just movie clips with odd filters
applied and garbage quality videos with clickbait titles and great thumbnails.
I do like the serendipity of finding something new sometimes. But my main view
should really tilt more toward what I've already said I want to watch.

It's pretty easy to make a version that does exactly that with RSS,
and as it turns out RSS is still available on YouTube. They even have the
headers on most pages that make it easy to find the RSS feed without having to
go digging around for it. So if you want to get the channels you care about 
from YouTube without allowing them to stop delivering the ones they don't feel
like giving to you - RSS is at least an option.

RSS reading options aren't as numerous as they once were. But there are some
good tools out there. Thunderbird has an option to add feeds into your inbox,
and I believe Outlook still has something to handle feeds in a similar way.
And when I looked at the App Center on my Ubuntu machine there were a few 
dedicated desktop feed reader apps that might work well. I wanted a project to
play with recently, so instead of just picking up an existing one I made a
very minimal command line reader called
[Feeder](https://github.com/mikerowehl/feeder). It's a command line tool that
tracks feeds in a minimal SQLite database, and it just writes out an HTML page
with the posts to read so I can open it in a normal browser. Works perfect for
my use. I'm sure it might be too simple for others. But might be a good match
for some so I figured I would share it.
