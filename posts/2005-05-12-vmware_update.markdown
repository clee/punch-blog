---
title: vmware update
published: true
---

Just thought I'd post a quick update about my situation re: my computer
at home, since I know you all care so much.

It turns out, after wiping my partition table and starting over from
scratch and getting Linux back up (which took all of about ten minutes),
Windows installed fine from the SATA DVD drive.

I have no idea how this is possible - [this page says][], and I quote:

<p>
> Out of the box, no current Windows version, including Windows Server
> 2003, supports SATA drives.

</p>
My best guess is that the BIOS enables some sort of PATA emulation that
Windows can use to find that drive. That's the only thing that makes
sense.

And I was a little hard on VMware, to be honest. I mean, I was using a
feature that [they specifically warn against most people using][], while
running 32-bit VMware on a 64-bit (unsupported variant of a) host OS.
I'm reminded of a quote here...

<p>
> People who do stupid things with hazardous materials often die.

</p>
Granted, I didn't exactly die, but I think it somewhat applies.

  [this page says]: http://www.windowsitpro.com/Article/ArticleID/41058/41058.html
  [they specifically warn against most people using]: http://www.vmware.com/support/ws5/doc/disks_instraw_ws.html
