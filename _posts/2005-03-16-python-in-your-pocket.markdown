---
date: 2005-03-16 14:31:50
layout: post
title: Python in your Pocket
---

[Erik Smartt](http://conferences.oreillynet.com/cs/et2005/view/e_sess/7020) about Mobile Python.

Apparently you can take a photo from the script, I missed what the UI looks like though.

import camera
i = camera.take_photo()
f.write(i)

I tried this out with the version of python I have and it doesn't look like there's a camera module.  Maybe there's an update?

The default interface to python is driven by a python script, default.py.  You can hack that to make it look whatever way you want. Erik has a tabbed interface for his version. Showed off OpenGL python also.  The code is ugly and eventually crashes the phone, but it works.

So what if you like scripting, but don't like python? Someone else had sent him a demo of Perl 5.8.6 on Symbian.

What if you were running a webserver and mod_perl and mod_python?  With access to the hardware, access to the local from a remote browser is pretty interesting. For instance, browsing from another phone.

Nokia continuing to develop, focus on next gen devices and modules for core device functionality. Location info. Not looking at XML parsers and generic Python functions.

Question about supporting other series of devices.  Will it support series 80?  Erik says he has no idea. The port of python itself is rather generic, done as a port to Symbian.  But in order to finish up the interface it needed to be hooked into Series 60 specific stuff.

Someone asked about a central place to share code, Erik said there isn't anything yet.
