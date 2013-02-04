---
comments: true
date: 2005-05-17 18:01:58
layout: post
slug: wordpress-151-conditional-get-breakage
title: Wordpress 1.5.1 Conditional Get Breakage?
wordpress_id: 509
categories:
- Open Source
---

Sorry to chuck this here, but I'm on my way off to meet up with some folks and don't have time to search out if this is a known issue or not.  It looks like the conditional get support in [Wordpress 1.5.1](http://www.wordpress.org) might be broken for some combinations of requests and maybe PHP versions. There's this check in wp-blog-header.php:




> if ( ($client_last_modified && $client_etag) ?
                ((strtotime($client_last_modified) >= strtotime($wp_last_modified)) && ($client_etag == $wp_etag)) :
                ((strtotime($client_last_modified) >= strtotime($wp_last_modified)) || ($client_etag == $wp_etag)) )




The problem is when there's no last modified header at all, so $client_last_modified is false, and we evaluate the second alternate of that conditional. For all the versions of PHP I've tried the strtotime() function treats false the same as "now" and returns the current time. Thus strtotime( false ) is always greater than the $wp_last_modified time. And I get odd responses like this:




> 
hole:~ miker$ more feedreq.raw 
GET /blog/?feed=atom HTTP/1.0
Host: www.thisismobility.com
hole:~ miker$ cat feedreq.raw | nc www.thisismobility.com 80
HTTP/1.1 304 Not Modified
Date: Wed, 18 May 2005 01:59:52 GMT
Server: Apache/1.3.31 (Unix) DAV/1.0.3 mod_gzip/1.3.26.1a PHP/4.3.10 mod_ssl/2.8.19 OpenSSL/0.9.6c
ETag: "2d0a68b8eeadb53e4597a041c96a83c8"
X-Pingback: http://www.thisismobility.com/blog/xmlrpc.php
X-Powered-By: PHP/4.3.10
Last-Modified: Fri, 13 May 2005 12:32:30 GMT
Connection: close
Content-Type: text/html



hole:~ miker$




No state headers at all and a 304 return? No wonder people were telling me they were having trouble with the This is Mobility feed. Anyone else seeing that, or did I mess something up and not notice? I thought I had a clean 1.5.1 install, but I've been known to flail and then forget about it.
