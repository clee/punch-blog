---
title: screeching handbrake
published: true
---

I really love it when I can easily find something that bothers me in a
piece of software, dive into the source, and start fixing things.

That's what I've been doing lately with this [little DVD ripping app
called HandBrake][] - it's a cross-platform GPL DVD ripper that makes it
almost painfully easy to take a movie from a DVD and turn it into a file
that you can watch whenever the need strikes you.

There are some problems, though. Right off the bat, there is the issue
that (when ripping a DVD) libdvdread spews out hundreds of lines of
output, warning me that a value isn't 0 and it should be. It's not
fatal, but it certainly is annoying, so I whipped up [this patch][] up
to fix it.

Also, I don't have a video iPod at the moment, or a Sony PSP (and I
don't see myself buying the latter anytime soon, but you know... if one
were to fall into my lap, I'd probably use it and enjoy the hell out of
it.) Anyway, not owning one of these devices, I'm more interested in
HandBrake as a way to make high-quality compressed archives of my DVD
movies that I can watch on the HDTV in the living room. There's a
problem, though; HandBrake scales the picture by default as it
transcodes it.

[Not anymore][], it doesn't. Now it has support for (optionally)
embedding the anamorphic pixel ratio into the output file, and can
preserve the original DVD video frames. Which means, with x264 at least,
a reasonable performance increase of about 15%. Not too shabby!

Unfortunately, the only GUIs for HandBrake are on Mac OS X and BeOS.
Now, I love BeOS. Haven't used it in years, though, and I don't even
think it'll run on my hardware; Haiku still isn't quite there yet,
either, but I'm keeping tabs on it. What I really wanted is a Linux UI
for HandBrake.

So, I've been hacking on one.

![Qt4 HandBrake UI][]

Stay tuned for more on this...

  [little DVD ripping app called HandBrake]: http://handbrake.m0k.org/
  [this patch]: http://c133.org/tmp/libhb-dvd.diff
  [Not anymore]: http://c133.org/tmp/enc-pixelratio.diff
  [Qt4 HandBrake UI]: http://c133.org/qhandbrake-1.png
