---
title: gstreamer hacking
published: true
---

So mpyne had implemented a somewhat working SPC plugin for GStreamer
which was pretty limited and somewhat useless. (As he admitted :)

His version had a hardcoded path to the SPC file, didn't work as a
filter - just as a src - and was performing quite strangely on his
system for some reason. I've since rewritten it (from scratch) as a
filter and not a src. It works on my system, kind of. I haven't gotten
the typefind implementation done yet, and it's pretty fragile at the
moment - I haven't figured out exactly why, but somehow removing a
printf from the spc\_setup function causes the plugin to segfault (I
think LoadSPCFile may be doing something strange, but I'm not sure...)

<p>
If you have tla installed, you can do:  

    tla register-archive http://c133.org/arch/tla get clee@kde.org--2004/gst-spc--filter--0 gst-spc

</p>
If you don't have tla, you can try poking around on the site but seeing
as how things aren't quite ready for mass consumption, I'm not making
any releases just yet.

Now, to go take a shower. All of those 'g's and '\_'s make me feel so
dirty.
