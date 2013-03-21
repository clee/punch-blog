---
title: dogtail unleashed
published: true
---

Today is a pretty cool day for me because a project I've been working on
at work is finally released.

[![Dogtail!][]][]

dogtail is a framework written in Python which makes it easy to write
scripts to automate graphical applications. It uses AT-SPI which means
that (for now) it doesn't work with KDE, but I fought the good fight to
make sure that it has no GNOME dependencies so that hopefully there will
be a chance of KDE adopting it in the future. Now that we've finally
gotten the release out the door, I plan to track KDE svn and write
scripts for KDE4 apps. Ideally, we'll have KDE4 support before KDE4 is
actually released.

(I know that there's a tool from [KDAB][] which allows one to automate
KDE apps, but it's not Open Source and it only works with KDE; dogtail
supports anything that we can see through AT-SPI, which includes
OpenOffice.org and Mozilla-based applications as well as, hopefully,
KDE4.)

  [Dogtail!]: http://people.redhat.com/zcerza/dogtail/images/dogtail01.jpg
  [![Dogtail!][]]: http://people.redhat.com/zcerza/dogtail/
  [KDAB]: http://wwww.klaralvdalens-datakonsult.se/
