---
comments: true
date: 2004-12-28 15:10:24
layout: post
slug: linux-bluetooth-obex-and-a-nokia-6600
title: Linux Bluetooth OBEX and a Nokia 6600
wordpress_id: 378
categories:
- Open Source
---

I've been having trouble with uploads to both [Flickr](http://www.flickr.com) and [BuzzNet](http://www.buzznet.com) during this vacation. I uploaded images the day I left for NY, and everything worked at 12:30pm PST. Then I landed in NY and tried an upload using the same phone using the same settings to the same accounts, and it doesn't seem to be working any more. And everyone is gone for the holidays it seems, so self service it is. I didn't have the OBEX bluetooth tools setup under Linux (I'm currently using Gentoo on my laptop). I've tried to install the slick-as-hell-sounding gnome-bluetooth package, but I can't emerge it. Error compiling. So I went tooling around looking for simple bare bones shims so that I could just move some data around. Not all that much out there.  I have GPRS working over bluetooth for this laptop and phone, so I know the basics are working. But how about accessing the data on the phone itself? Not good, here's some info.





I grabbed the [OBEX push daemon](http://oss.bdit.de/opd.html) and installed that.  First I had to install the deprecated bluez-sdp package under Gentoo, but OPD compiled and worked fine after I set it up. Last release of this package was during 2003.  Wow!!! Is everyone else using Bluetooth under Linux using gnome-bluetooth to handle inbound pushes? I didn't really find much else that would do it. OPD worked great for getting images off my phone, sending from the phone. I wasn't able to get file transfer working, I assumed that I should be able to use obexftp to browse and get/put files from my laptop, but no go. I try any command line and it just seems to fail. None of the info I found online says that special effort is required, but I get errors trying to list anything at all:





> 
miker@whirr src $ obexftp -b 00:60:57:8A:E7:5B -B 10 -l /
No custom transport
Connecting...bt: 1
failed: S45 UUID
done
Receiving /... failed: 
Disconnecting...done
miker@whirr src $ 






I also couldn't get the get function using [OpenOBEX-apps](http://prdownloads.sourceforge.net/openobex/openobex-apps-1.0.0.tar.gz) working either. Does OBEX file transfer expose a different namespace for files than something like [FExplorer](http://www.newlc.com/article.php3?id_article=70) does? Should any of these applications work? Pushes over OBEX are all I've ever really gotten working. Does OBEX file transfer just suck too much for anyone to ever get it working? I thought the Windows Bluetooth drivers normally allowed browsing and access to the info on the phone. I doubt the Windows users are typing in magic paths... so this should be technically possible. Anyone know of a simple ftp style app to access a Series60 phone (or any OBEX capable device) from Linux?  And if not, anyone know if it's possible to do without installing an app on the phone? I'll write it if the app doesn't already exist, I just don't feel like pouring time into figuring out that the underlying technologies are too broken to get this working.





I was also looking for how to push files from the laptop to the phone, and I found lots of people pointing to my old site, unrooted.net, which is no longer up. I need to put that back, but in the meantime I put up [the ussp-push](http://www.bitsplitter.net/projects/ussp-push-0.2.tgz) package here at Bitsplitter. It has an obextool command line app that does a push from a Linux system out to a device that accepts OBEX push. You can also use obex_test from the openobex-apps package. Here's an example of pushing an image from my laptop to my 6600 using that package:





> 
miker@whirr src $ ./obex_test -b 00:60:57:8A:E7:5B 10
Using Bluetooth RFCOMM transport
OBEX Interactive test client/server.
> c
Connect OK!
Version: 0x10. Flags: 0x00
> p
PUT file (local, remote)> ./ed.jpg edbg.jpg     
name=./ed.jpg, size=2756
Going to send 2756 bytes
Made some progress...
Made some progress...
PUT successful!
>

