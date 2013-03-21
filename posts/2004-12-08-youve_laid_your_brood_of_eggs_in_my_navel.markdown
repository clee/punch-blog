---
title: you've laid your brood of eggs in my navel!
published: true
---

Found out something mildly amusing today.

Apparently nobody has bothered building anything from the xlibs or
xserver trees on an AMD64 system yet.

These modules contain such gems as:  
\# if defined(\_\_AMD64\_\_) || defined(AMD64)

Which doesn't actually \*work\* on these machines, as gcc defines
\_\_amd64\_\_ and not AMD64. (Yeah, kids, case matters.)

Daniel added me back to the xlibs and xserver groups, so I should be
able to commit some fixes for this stuff; however, there are still a lot
of other issues on AMD64 that haven't been fixed yet. ::sigh::
