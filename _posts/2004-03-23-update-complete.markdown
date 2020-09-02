---
comments: true
date: 2004-03-23 20:45:54
layout: post
slug: update-complete
title: Update Complete
wordpress_id: 209
categories:
- General
---

And here you have it, the updated Bitsplitter Blog. The minimalist view is still the default, but now featuring such coolness as [valid XHTML](http://validator.w3.org/check?uri=http%3A%2F%2Fwww.bitsplitter.net%2Fblog%2F), [valid CSS](http://jigsaw.w3.org/css-validator/validator?uri=http://www.bitsplitter.net/blog/), and a [valid RSS2 feed](http://rss.scripting.com/?url=http%3A%2F%2Fwww.bitsplitter.net%2Fblog%2Fwp-rss2.php). And this time instead of destroying the normal setup, I left the [desktop version available](http://www.bitsplitter.net/blog/desktop.php) as well. So those of you who are into that kind of thing should be made a little happier.

My [test posting from Vagablog](http://www.bitsplitter.net/blog/index.php?p=204) worked, but I got the standard XML declaration error instead of a success message. It turns out that this has been fixed for real in CVS for [WordPress](http://wordpress.org), but the 1.0.2 version still barfs some stuff that it shouldn't into the XMLRPC output. If you want to fix it on your own, and you know what you're doing, find the wp_set_post_cats() function in xmlrpc.php. Go to the part that reads:


> 
// First the old categories
$old_categories = $wpdb->get_col("SELECT category_id FROM $tablepost2cat WHERE post_id = $post_ID");



Just after the assignment of $old_categories add the lines:


> 
if ( !isset( $old_categories ) ) {
$old_categories = array();
}



That should take care of it for now. The 1.0.3 release should have the fixes from CVS, so that should be the last of that issue.

