---
title: NetworkManager and KDE
published: true
---

[Fab][]: NetworkManager actually has a pretty well-designed separation
between the front-end and the back-end; the only problem stalling us
from being able to do cool things with it right now is that we have no
working DBUS bindings for KDE3 (so nobody can easily write a Kicker
applet to interface with NetworkManager to use on their desktop
**today**), and KDE4 doesn't actually have anything usable at this
point, whatsoever.

I brought this up at aKademy - aseigo and I were basically ready to go
ahead with it but we got sidetracked with window icon previews in the
window list on the desktop pager hover tooltip. (Try saying that five
times fast.)

In theory, somebody could write the applet using the DBUS API from C,
but the current Qt bindings in the DBUS tree are pretty much worthless,
so it's not going to be pretty either way.

  [Fab]: http://www.kdedevelopers.org/node/1465
