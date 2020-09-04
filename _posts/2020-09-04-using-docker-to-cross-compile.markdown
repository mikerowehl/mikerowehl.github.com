---
layout: post
title: "Using Docker to Cross Compile"
date: 2020-09-04 13:57
---
I've been poking around with a bunch of low level programming stuff. Looking
at old source code and playing with some newer examples, like
[Alex Parker's fantastic example of a boot loader with assembly and C++](http://3zanders.co.uk/2017/10/13/writing-a-bootloader/).
There's lots of interesting stuff out there. But I never like having to setup
a cross compiler on my system. I used to do a ton of that, and the toolchain
would always get messed up somehow.

So I considered just playing around with any of this low level compiling stuff
inside a Linux VM. Not fantastic, but I'm sure it would work well. But then I
realized that really all I needed was an isolated toolchain, so that should be
something worth setting up in Docker. The more I thought about it the more it
sounded like a great idea. A great enough idea that I was sure someone had
thought about it and done it already.

Check out the [dockcross](https://github.com/dockcross/dockcross) project for
a fantastic example of a cross compile toolchain in a Docker container. They 
have a bunch of supported target systems and a nice wrapper script that makes
it easy to call the toolchain as if it was running locally. I used the
dockcross/linux-x86 image to compile the examples from Alex Parker's blog
posts. I'm still running nasm locally, but the compile and link are done using
the tools from the docker image. Slightly different command line, but I think
that's just caused by different defaults. I haven't fully gone through all the
options, so I can't vouch for them being correct for all cases. But they leave
you with a running boot sector that loads a routine from C++:

<script src="https://gist.github.com/mikerowehl/ffaad752adc98a6286c6297d0a63c44b.js"></script>
