---
layout: post
title: "FirefoxOS 1.2 on ZTE Open"
date: 2013-10-24 18:06
comments: true
categories: 
- Mobile
- Engineering
- Open Source
---
I picked up a [ZTE Open](http://www.engadget.com/2013/10/03/zte-open-review/)
Firefox OS device a little while ago. Given that
[developer hub](https://marketplace.firefox.com/developers/dev_phone) says
it's a "powerful device aimed at developers and early adopters worldwide" I
figured it would be good for some hackery. I read the specs, so I knew that
"powerful" should be pretty suspect. I was surprised to find out that it's not
really for developers, and increasingly doesn't seem to be all that open.

When I first grabbed it I figured maybe I could use it to just get a feel for
FirefoxOS and the direction the teams were trying to push for. However, the
phone ships with a 1.0.0 version of the operating system and some major basic
features were missing to even use it for a day or two. For instance GMail
contact syncing shows up in FFOS 1.1 (I'm not a Facebook user, so syncing using
the one existing mechanism wasn't an option). Since this was supposed to be
a developer phone for early adopters, I figured that would be easy to remedy.
Not so, there's no official OS updates for the phone planned at all. Weird.

Okay, no problem, I'll use it to just do a little poking around developing
using the Gecko/Gaia stack and getting a feel for it on real hardware. However,
trying to push an app from the simulator it never showed up on the phone.
Rebooted and it popped up. Turns out there's a
[race condition bug in FFOS 1.0](https://bugzilla.mozilla.org/show_bug.cgi?id=842725)
which really keeps it from being usable as a developer platform. 
Of course the pages talking about it say you should "make sure you have the
latest version of Firefox OS on your devices". Which we just established
isn't possible for this developer device, at least not according to ZTE.
Well ain't that just a kick in the crotch?

So of course I ended up doing what I said I wasn't going to do, and dove
straight down the rabbithole of compiling my own recent version of Firefox OS
from source and getting it installed on my ZTE Open device. Turned out to be
way more of an involved process than I expected given that the device is named
the "ZTE Open". I expected that to mean developer friendly. Together with the
Firefox site saying the device was aimed at developers, I didn't see any
reason to second guess that assumption. Here's the process I went through
though, which should get you going from an unboxing to running FFOS 1.2 on
your device. The process isn't too horrible, but making sense of lots of the
existing posts out there and figuring out the right order for a fresh device
took some experimentation.

The first thing to do is apply the
[update from ZTE](http://www.ztedevices.com/support/smart_phone/b5a2981a-1714-4ac7-89e1-630e93e220f8.html?type=software).
This was one of the hardest parts to puzzle out for me. Turns out the firmware
on the model I had was old enough that it was failing to flash the images once
I had them built. There were folks posting that they had gotten certain parts
working, and it was failing for me and others who had recently purchased
devices. Turned out that the original firmware didn't support fastboot, which
is one of the mechanisms for getting the code actually onto the device. That
V1.0.0B02 release from ZTE has instructions for how to load it using the stock
recovery image, and once it's installed you'll be able to use the simple tools
to get your code onto the device. Also nice, with the ZTE provided update.zip
on your SD card you can use recovery mode to get back to a working system if
you end up screwing up the system partition. Which I did dozens of times.

Once you have the ZTE update in make sure you have debugging turned on for
your phone. Go into Settings / Device Information / More Information / 
Developer and flip on the Remote Debugging option if it isn't on already.

Next, unfortunately, you'll have to grab a binary image of the
[boot partition](http://sl.edujose.org/2013/10/adapted-boot-image-for-use-with-b2g.html)
hacked up and ready to use. This is horrible, and it's the other part that was
really a sticking point trying to figure out. As you'll see later on, for some
reason the boot2gecko build for the inari device (which is the name you use
for building for the ZTE Open) doesn't generate a boot.img. From what I can
tell it doesn't even generate the parts necessary to pull together into a
boot.img. And as I found out through multiple tries, putting the system and
user partitions from a custom build together with the boot from a stock system
you'll generally end up with the OS booting and the UI layers crashing 
repeatedly. That's what I got at least.

Once you've got that stuff the build is pretty much as described in the
[FirefoxOS build docs](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox_OS/Firefox_OS_build_prerequisites).
I use an OS X system, but I did my build in a VMWare VM running Ubuntu 13.04.
The tools used to interact with the Firefox OS devices are the same as used
for Android development. And I've done that under a VM tons, so I was pretty
comfortable with that part of the setup. Plus being in a VM meant I could muck
with the stuff in the Linux install as much as I wanted. Below is the actual process I
ran through, getting all the tools in place, configuring, and building. This
assumes you're starting from a completely fresh 13.04 install, you run through
the installer and then let it pull down any updates, then do this:

<script src="https://gist.github.com/mikerowehl/7275342.js"></script>

NOTE: I moved the set of commands to run off to a gist cause Octopress was 
prettying up the quotes and making them cut/paste unfriendly.

And then you should have a FFOS 1.2 install runnable on your device. I tested
mine out with my TMobile SIM in the US: phone works, SMS works, data connection
works (though by default it was disabled on mine, just use the notification
pulldown and toggle the cellular data option right next to the wifi toggle).
Hopefully as the device and OS evolve this gets a lot easier and more developer
friendly. Needing to pull a binary boot image from someone else just to get a
fresh build onto a device, that's not good. I was expecting FFOS development
to show up Android development in terms of encouraging developers to work with
the base system. Not the case so far.
