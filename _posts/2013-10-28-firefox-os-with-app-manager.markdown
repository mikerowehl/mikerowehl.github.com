---
layout: post
title: "Firefox OS with App Manager"
date: 2013-10-28 10:46
comments: true
categories: 
- Engineering
- Mobile
- Open Source
---
One of the nice things about
[getting FFOS 1.2 on my device](http://rowehl.com/blog/2013/10/24/firefoxos-1-dot-2-on-zte-open/)
is being able to use App Manager instead of the simulator plugin to do
development. Given that
[the App Manager replaces the Simulator Dashboard](https://hacks.mozilla.org/2013/10/introducing-the-firefox-os-app-manager/)
in the newest versions of Firefox, it seems like the kind of thing developers
should have access to. So hopefully ZTE figures out a way to get a 1.2+
release on their developer phones.

Note however that the app manager is available in the Firefox 26 series, which
is [current the pre-alpha release](http://www.mozilla.org/en-US/firefox/aurora/).
You can install Aurora side by side with the current stable Firefox release
(that's the default on OS X at least). The app manager is available without
having to install anything, but you'll need to install the ADB helper to
connect to an actual device. Details are in the
[using the app manager](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox_OS/Using_the_App_Manager)
document. I've been testing it out primarily with my locally built FFOS 1.2 on
the ZTE Open (inari) device.

Now comes the hard part of trying to figure out what you can put on the
device to make sure everything is working before you dive too far into
hacking around on your own. You'll probably run across things like
[the Firefox OS Quick Start example](https://github.com/mozilla/firefoxos-quick-start)
and the [Mozilla templates for Open Web Apps](https://github.com/mozilla/mortar).
None of those seem to be working to generate something you can install on
a device (they work great for the simulator, running on the same machine as
your development tools). Seems like there haven't been a ton of folks working
with physical devices yet.

This
[Firefox OS boilerplate app](https://github.com/robnyman/Firefox-OS-Boilerplate-App)
serves as a fantastic starting point however. Just a clone and then
"Add Packaged App" in the app manager and you'll be able to refresh and run
on the device. There's some rough bits, like geolocation isn't working within
the app on my device, and "Take picture" has some issues. However I can 
"Pick image" and choose camera as the source and that works okay. And the
rest of the stuff like vibrate, ambient light, device orientation, and check
battery are all working.
