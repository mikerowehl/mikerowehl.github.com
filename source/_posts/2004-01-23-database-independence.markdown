---
comments: true
date: 2004-01-23 16:19:42
layout: post
slug: database-independence
title: Database Independence
wordpress_id: 127
categories:
- Open Source
---

There's a [post by John Udell](http://weblog.infoworld.com/udell/2004/01/23.html#a895) about database lockin. I think the issue with SQL dialect lockin is probably more troublesome. I agree that transport independence is a problem though. Databases have been like this for a long time - a standard language to query them, but different libraries for the different databases to actually access them. There's probably some issue in there that I'm not aware of that keeps it from happening, but why isn't there a standard transport? ODBC is cool, but it's a shim on the application end to allow different drivers to be swapped in as needed. At least in all the uses I have seen. Is there an "ODBC native" format that can be used by an RDBMS? I'm thinking probably not. And if so, why is no one using it? For the proprietary systems like Oracle and DB2 I could certainly see why, they don't want people to be able to switch easily. But for open source databases why isn't there transport level standardization? Any database gurus out there who might know the answer, please chime in. I vaguely remember something about an XML based query exchange from a number of years ago. That ever make it anywhere?
