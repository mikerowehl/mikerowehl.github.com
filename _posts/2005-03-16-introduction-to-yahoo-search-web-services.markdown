---
comments: true
date: 2005-03-16 15:22:44
layout: post
slug: introduction-to-yahoo-search-web-services
title: Introduction to Yahoo! Search Web Services
wordpress_id: 460
categories:
- General
---

[Introduction to Yahoo! Search Web Services](http://conferences.oreillynet.com/cs/et2005/view/e_sess/7033)

People always suggesting things to do, WS is our way of saying "Great, those sound like great ideas, show us!" Also want to test the waters, the way that any project has a particular flavor they want to find out what kind of project the Yahoo APIs will turn into.

obLink: [http://developer.yahoo.com](http://developer.yahoo.com)

Docs, SDK, Wiki, Blog, Lists. REST interface to search can be seen as just the first step, there will be more.

5,000 queries/day/service, IP restricted. Non-Commercial use. IP based so that you can share applications with friends, you should be able to distribute your app without causing the user to go sign up for a login or anything. If you go over your limit, you get locked out for a day.

Example app: [ImageSearchBuzz](http://buzz.progphp.com/) ([desc](http://toys.lerdorf.com/archives/33-Buzzing-the-Yahoo!-Search-Web-Services.html))

You can actually get RSS out of Yahoo searches.  The same service that outputs the API results can output RSS.  Actually, RSS is available already for the Yahoo search pages. [like this](http://api.search.yahoo.com/WebSearchService/rss/webSearch.xml?appid=yahoosearchwebrss&query=bitsplitter&adult_ok=1).

Apparently somewhere there's a query based on longitute and lattitude, it's in the documentation somewhere.

Tags: [ETech2005](http://www.bitsplitter.net/tag.php/etech2005)
