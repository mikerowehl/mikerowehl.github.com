---
layout: post
title: "ktool for Building OSDev Samples"
date: 2020-09-10 13:53
---
The other day I packaged up
[a build of cross-compile tools for i686 bare images](https://github.com/mikerowehl/ktool)
using the
[instructions from the OSDev wiki](https://wiki.osdev.org/GCC_Cross-Compiler)
for making a cross-compiler suitable for building bootable images and kernels.
I had started fooling around with dockcross to do the builds, but some of the
OSDev samples explicitly complain if you use a compiler that can be used to
build for a Linux target. So I just packaged up something of my own and made
a super simple wrapper script to make it less cumbersome to run.

Today I added a few tools so that it'll easily build a workable image for the
[Meaty Skeleton sample](https://wiki.osdev.org/Meaty_Skeleton) with very
little setup required. Here's how to do it from a clean system (with Docker
already installed):

<script src="https://gist.github.com/mikerowehl/85ba878ef3b22b0154256f9bbcd04ee9.js"></script>

I like the way it worked out. At first the Docker image was huge cause I did
the tool download, build and cleanup as different steps. Now there's a big
and kinda ugly stage in the Dockerfile to download, build, install, and then
clean up all as one big chunk. But the result is a relatively trim container
that makes the startup a lot simpler.
