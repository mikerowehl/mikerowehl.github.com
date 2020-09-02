---
date: 2004-04-18 12:34:16
layout: post
title: Web Programming with Lisp
---

I found a [three part article about web programming with Scheme](http://www.double.co.nz/scheme/modal-web-server.html) linked off the [Finding Lisp blog](http://www.findinglisp.com/blog/). The articles themselves are very good, and they led me to [Chicken Scheme](http://www.call-with-current-continuation.org/index.html), an interesting Scheme implementation I was able to get running on my ancient laptop so I could play with something on the plane trip home. It includes what seems to be an interesting [mechanism to support extension](http://www.call-with-current-continuation.org/manual/manual-Z-H-51.html#%_chap_7), something I haven't seen in other implementations yet. Chicken provides a cover script that can be used to create, build, and install extensions called "eggs". Getting the extra modules needed to do web programming was a cinch.
