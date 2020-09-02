---
comments: true
date: 2004-02-09 06:29:45
layout: post
slug: some-more-clustering-tools
title: Some More Clustering Tools
wordpress_id: 158
categories:
- Open Source
---

A [Linux Gazette article about Hybrid Clusters](http://www.linuxgazette.com/node/view/8468) mentions a couple of cool tools that I didn't know about. In particular, the [DRBD](http://www.linbit.com/en/article/view/46/1/11/) package looks great. In the past few weeks I've run across [Clustered JDBC](http://c-jdbc.objectweb.org/) for the first time as well. c-jdbc looks like a great package, but applies only to databases being used through JDBC (of course). DRBD is a block device for Linux which can replicate information on the fly for any full block device. There are tradeoffs in both directions, such as being able to use c-jdbc in active-active clustering across two or more servers, but with DRBD having applicability to more datasets; but the important aspect is that there are two great open source and free technologies that can be used to fulfill what is a very high-end clustering capability. Also mentioned is a set of scripts for managing failover, called TKCluster. IP address takeover and automatic failover always end up being more complex issues than they look like on the surface, it's nice to have working samples to start from. Would be nice if there were some docs to go along with the package itself. This article seems to serve as the [project page](http://www.solidrocktechnologies.com/clustermanager/) as well. The code in there seems to be quite clean though, and I don't mind working like that. But lately I've found myself spending more time writing more docs for packages I pick up than doing actual work, so unfortunately that has tainted my view in general.
