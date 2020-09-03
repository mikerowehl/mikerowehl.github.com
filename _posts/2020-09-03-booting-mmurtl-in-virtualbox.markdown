---
layout: post
title: "Booting MMURTL in VirtualBox"
date: 2020-09-03 12:50
---
I was looking through some of the old books on my bookshelf when I ran across
my copy of 
[Developing Your Own 32-Bit Operating System](/assets/images/32bit_os_book.jpg).
I spent a bunch of time playing around with the code when I picked up the book,
uh... more than 20 years ago. Wow.
Eventually Linux took over a lot of that interest however and I haven't looked
at the book in decades. It was a wonderful learning system that I picked up a
ton of experience from. And that was back before we had decent emulation and
virtualization services to work with. I wondered if the code was still floating
around and if anyone was using it.

I was excited to see that Richard Burgess has
[a site up with the source and a PDF of the book](http://www.ipdatacorp.com/mmurtl/).
And the site encourages folks to share and contribute, so there's a
[copy up on GitHub](https://github.com/the-grue/MMURTL-OS) that's a bit
patched up and includes some binary images. Yay!

I believe it has been just over 20 years since I used MMURTL. So I wanted to
just boot the thing up and refresh my memory before I dug in too much. Best
place to start I figured was one of the
[floppy disk images](https://github.com/the-grue/MMURTL-OS/tree/master/images)
that the grue was nice enough to publish in his repo. I created a new DOS
machine in VirtualBox and attached the floppy image, and I did get the
MMURTL monitor kinda up. But partially cause I didn't remember how things
worked and partially cause of some quirks in the setup it took a few tries.

If you're trying to do the same thing and run into issues using the images
with VirtualBox there are two gotchas to keep in mind. First off, if you
create a machine in VirtualBox and attach a new disk image to it for the
hard drive, that hard drive image is completely uninitialized. MMURTL doesn't
handle that well. So at first I was having a problem where MMURTL would start
up and scan through devices, but fail while it was setting up the hard
drives. A quick scan through the source made it obvious that the setup was
failing cause there was no partition table. So I removed the hard disk image.
But then the setup was failing cause there was no hard drive. What I ended
up doing was attaching the blank hard disk image to a Linux VM I already had
configured and using that to partition the drive. Then I reattached it to the
MMURTL VM and it finished booting up. Yay!

But when it booted up it just sat there. That wasn't what I remembered from
when I had been experimenting years ago. It wasn't completely obvious from
what was on the screen what was going on. When MMURTL first boots up it's in
a monitor program (described in chapter 11 of the book, starting on page 142)
and you need to use one of the function keys to get it to display some info
or launch into a CLI. The F1 key launches the CLI, which started up fine for
me and dropped me where I expected to end up!

Now that I think about it, I believe I had just configured the default job
file for my monitor to launch into a CLI automatically all those years ago.
So the behavior from the image posted is probably totally reasonable.
Still, in case you're coming into this fresh I figured this could be a 
useful tip.

I have no idea what I'll end up doing with this. I have been doing some 6502
single board hackery. And that did get me a bit fired up again for doing some
low level work. Not sure if I'm fired up enough to get myself fully back into
proper Linux kernel dev. But maybe hacking around a smaller system like this
would be some fun.
