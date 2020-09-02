---
comments: true
date: 2006-03-05 21:59:28
layout: post
slug: writing-a-web-service-interface-on-ning
title: Writing a Web Service Interface on Ning
wordpress_id: 627
categories:
- General
---

Like I was babbling about yesterday, I've been [thinking about different ways of hooking up mobile applications and web applications and trying to bridge the gap](http://www.thisismobility.com/blog/?p=107). One area that gets a lot of leverage relatively quickly is implementing de-facto standard web service interfaces that the mobile applications can hook up to. There are both desktop and mobile applications that interact with the [Blogger API](http://www.blogger.com/developers/api/1_docs/), [Flickr Services](http://www.flickr.com/services/api/), the [Atom Publishing Protocol](http://www.ietf.org/html.charters/atompub-charter.html), etc.





Yesterday while chatting with Russ I decided to try setting up an application that would accept posts from the Nokia [Lifeblog](http://www.nokia.com/lifeblog) app. Russ pointed me at [Robert Price's description of getting Lifeblog posting to his site](http://www.robertprice.co.uk/robblog/archive/2005/2/Lifeblog_Posting_Protocol_Example.shtml). Simple enough. My version is up at [lifeblog.ning.com](http://lifeblog.ning.com/). Although it's currently nothing more than a sample, it's on Ning so it's easily clonable and hopefully will encourage some experimentation. It also shows off some interesting parts of [Ning](http://www.ning.com) in general.





One of the common misperceptions about Ning is that you can only clone the applications that we have available. That's not true at all, and everything I did to setup the Lifeblog sample I did as a normal user of the system. Here's a rundown of some of the general techniques and some tips for setting up a web service interface if you have an app on Ning.





**Returning Non-HTML Content**





Normally when you generate some HTML output on the Ning playground your bare content is wrapped with the xn_header.view header and standard sidebar before going back to the user's browser. If we're going to be generating responses to web services requests we obviously don't want to get that stuff jammed into our responses. No problem, Ning only decorates HTML content. Just set the appropriate header to mark your output as XML and it'll go right back out to the client unmodified. In this case I'm returning Atom responses, so I send application/atom+xml as the content type:



`header( "Content-type: application/atom+xml" );`



**Returning Non-200 HTTP Response Codes**





You can also use header() to send response codes other than 200 back in the HTTP status line. Good, cause the Atom docs for Lifeblog say that the app wants a "201 Created" response back from a successful post. Just a different form of header line, and that also makes it back to the client:



`header( "HTTP/1.1 201 Created" );`



**Appending The xn_auth=no Parameter**





Okay, this one is specific to Ning. The way we handle authentication across multiple applications all under the same ning.com domain without requiring a user to sign in for every one - while still providing security between applications - does cause a problem for this particular class of access. Normally when you make a request via browser to the Ning site a set of redirects are done to set some cookies and get a session prepared. We really don't want to do that however, we just want to get our request through and get outta there. Once again however, [a mechanism already exists to tell the system we don't want any of the normal session setup](http://documentation.ning.com/group.php?FAQGroup:title=General+Questions+about+Development#faq-700377). It was put there when we discovered problems with some RSS feed readers following the redirects, but it'll work perfectly fine for our purposes as well. Whenever specifying an endpoint for a service there should be an xn_auth=no parameter present to prevent the redirects.





**Processing a Raw Request Using SimpleXML**





The requests that come in arrive as XML documents posted against the script we write. So, how do you read in an XML document in PHP? Normally the variables for requests are in the $_GET or $_POST variables. Well, you read in a document like this:



`$data = file_get_contents('php://input');`



That's not a Ning specific thing, it's the mechanism PHP provides to access the raw content of a POST. So, now that you've got the raw content how do you handle it? The easiest way is probably [SimpleXML](http://www.php.net/simplexml), which generally really lives up to the name:



`$xml = @simplexml_load_string($data);`



That parses the posted document into an object that can be used to pull the text, elements, and attributes pretty simply:



`$title = (string)$xml->title;`



**More Stuff Later**





My simple sample doesn't really process all that it should out of the Lifeblog requests. Once I have another weekend to hack on the stuff I'll get it doing things like aggregating the multiple requests sent for each post into a single unit for storage and display. Authentication would also be nice to support. Although I do like anyone being able to throw content in, it's definitely not appropriate for all cases. Prudes. And that should show off some additional stuff like namespace handling in SimpleXML (which is actually [surprisingly elegantly done](http://www.zend.com/php5/articles/php5-simplexml.php#Heading3)) and handling custom HTTP headers for dealing with WSSE. Soon... probably ;-)
