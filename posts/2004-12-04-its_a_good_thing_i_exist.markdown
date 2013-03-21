---
title: It's a good thing I exist!
published: true
---

(Mixing some Zim quotes in now...)

Michael Pyne, brilliant guy that he is, was trying really hard to get
this SNESAPU code working on his system. I couldn't even get the crap to
compile, let alone to run and dump a bunch of zeroes like he was
getting.

I had mpyne tar up his work and send it my way to see if I could find
anything new. About forty-five minutes later, after we'd both looked in
a lot of unrelated areas, I found the missing link: A call to ResetAPU.
Added that in, and all of a sudden, it works!

Now, that wasn't enough. Since I finally have this library compiling,
and running, I don't want to simply dump the first five seconds of every
SPC to a wave file named output.wav. I want to play them to my speakers!

Having no prior experience with libao, but remembering somewhat vaguely
that the API didn't look too disgusting, I decided to try to get
SPC-\>libao output working. And now, just under an hour later, [I have
it working][]. And I even cleaned up the code a little bit so it's not
quite as embarrassing.

This code probably won't do most of you any good, but this is mostly for
mpyne's benefit as I'm not convinced I'll still be conscious when he
gets back. However, if you are interested in playing with it, you can
[grab the tarball][] from my site. You'll need g++ and nasm to build the
stuff, and since most of it's in assembly, you'll need to be on x86.

  [I have it working]: http://c133.org/tmp/spcplay.cpp
  [grab the tarball]: http://c133.org/files/snesapu-linux.tar.bz2
