---
comments: true
date: 2005-12-22 21:41:25
layout: post
slug: transfering-videos-to-an-ipod-under-linux
title: Transfering Videos to an iPod Under Linux
wordpress_id: 597
categories:
- Open Source
---

Getting [audio on to the iPod using Linux was a snap](http://www.rowehl.com/blog/?p=596). Getting videos on took a bit more doing, but also worked out quite well. I'm listing the info here cause it took a little searching around to find it. This is the stuff you'll need you probably don't have:







  * [gtkpod and libgpod](http://www.gtkpod.org/downloads.html)


  * [mp4v2 from the mpeg4ip project](http://mpeg4ip.sourceforge.net/downloads/index.php)





You also might need libid3tag, libtool, flex, and the development headers for glib and gtk.  I'm using Ubuntu 5.04 and was able to apt-get everything I was missing from the default install except for the stuff above. At the time of this writing the libgpod lib was at version 0.3.0, gtkpod was at 0.99.2, and mpeg4ip was at 1.4.1. I downloaded official versions of all, not a checkout from CVS or a development snapshot.





I had tried to download a video (my test video was the iPod version of [The Good, The Bad, and The Man](http://clerks2.com/?p=48), how do you like that for a test biznatch?) to the iPod, but it failed silently. Then I took a look at the changelog for gtkpod and saw that video support was added after the version I had. So I downloaded the newer drops and compiled, but didn't have mp4v2 at that point. This time I got an error that the lib was required in order to download files of .m4v type. After I compiled the lib, reconfigured and built gtkpod, everything was smooth after that.
