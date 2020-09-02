---
layout: post
title: "Finished a Program 29 Years Later"
date: 2013-11-19 22:20
---
My parents were getting ready to sell their house a few months ago, and
while I was there I grabbed a few 
[super old computer books](https://twitter.com/miker/status/330731191168806912)
from when I was a kid. Nostalgia I suppose, and I figured they would be cool
to have around. What I didn't expect was that I would find a printout and a
few pages of handwritten notes from a program I was working on when I was 9.
But of course, once I did, the only rational response was to see if I could
finally get it working. Which it now is.

While I know it definitely isn't
the only 6510 related project on Github, I have to assume it's one of a very
small number of CBM Basic programs. It's a
[6510 assembler written in Basic](https://github.com/mikerowehl/c64-assembler/blob/master/assembler.bas).
The Commodore 64 was the machine I had when I started to really get into 
programming. When the thing booted up it had Basic burned into ROM, which was
a fantastic way to get things going. But I knew what was really going on 
underneath was all machine language, and that the real programmers wrote in
assembly. The Commodore 64 didn't come with a built in assembler or machine
monitor, like some of the other 8 bit systems at the time did. And we didn't
have a ton of money, so getting one of the commercial assemblers at the time
wasn't really an option. So I figured I would write my own.

I actually spent tons of time manually compiling instructions and poking them
into memory back then, which was insanely educational. I forgot how close we
were to the hardware all the time back then. And trying to work out how to
build an assembler on my own was probably a fantastic set of experience to
have built up. I ended up getting my hands on a commercial assembler
eventually though, and never really finished up my own version.

Like most programming problems, the issue wasn't really with the code, it was
with the data abstractions.
The program was actually functional as it was, it was just kinda buggy, and
relatively convoluted cause it was trying to parse the operands to figure out
which instruction to use. I wanted to get the program working, but I didn't
want it to take me too long either. So I ended up cheating and used
non-standard mnemonics for the instructions to pack info about addressing mode
and index registers into the opcode instead. For instance instead of using
"cmp ($1a,x)" for indirect indexed addressing I swapped to using "cmpix $1a".
The expressiveness is the same, it just means I can pull in a token at at time
without any need to apply logic. The thing really becomes just a lookup table.

So in a grand total of about 45 minutes, including the time to figure
out how to use the VICE emulator and load Basic programs into it without
having to type it into the emulator, I had a working program that was able to
run the example code I had been trying out 29 years ago. I think if 9 year old
Miker could see that 45 minutes of hacking and the result he would be pretty
impressed.
