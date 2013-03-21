---
title: unexpected results
published: true
---

Red Hat, my employer, has a site license for VMware. (Well, either a
site license, or an assload of Workstation licenses, I'm not really sure
what the details are.)

I decided "Hey, why not play with the new release? You've got new
hardware. Maybe VMware will run acceptably fast on it!"

Man, what a fucking brilliant idea that was.

Backstory: I haven't booted Windows in a few months, not since Doom3
came out and wasn't available initially on Linux. However, I have some
shiny new devices in the new box, including a SATA DVD burner, which so
far doesn't seem to work with Linux very well. Ubuntu's kernel enables
SATA ATAPI support, which Jeff Garzik tells me is a bad naughty thing of
them to do since it's not ready yet. Which results in my ability to
\*see\* the drive on /dev/scd0, if the planets align properly, but I
can't actually use it for much.

This machine doesn't have a floppy drive, since I'm a cheap bastard, and
I happen to agree with Apple on this one. Fuck floppies. They should
have died a long time ago. I also refuse to run Windows XP - I bought
and paid for Windows 2000, a long time ago in a galaxy far far away, and
it's the last release of Windows that I really plan on ever using.
Windows 2000, being rather old, has some deficiencies, however. Like not
having SATA support in the installer (unless you load a driver from a
floppy, which I don't have).

I think to myself, "Hey! VMware! Raw disk support! It used to work
pretty well, why not try doing an installation from a virtual machine
into a physical disk? You can use the VM to download drivers, then
create a new hardware profile, reboot into it, and maybe that'll work."

HAHAHAHAA

Let's just say that this was probably the worst idea I've had all night,
even worse than eating that third slice of pizza. My partition table on
/dev/hda now looks like this, thanks to VMware:

<p>
    Disk /dev/hda: 41.1 GB, 41174138880 bytes16 heads, 63 sectors/track, 79780 cylindersUnits = cylinders of 1008 * 512 = 516096 bytesThis doesn't look like a partition tableProbably you selected the wrong device.   Device Boot      Start         End      Blocks   Id  System/dev/hda1   ?      216399     1904881   850995205   72  UnknownPartition 1 does not end on cylinder boundary./dev/hda2   ?      723265     1262922   271987362   74  UnknownPartition 2 does not end on cylinder boundary./dev/hda3   ?      167316      167316           0   65  Novell Netware 386Partition 3 does not end on cylinder boundary./dev/hda4         2671568     2671619       25817+   0  EmptyPartition 4 does not end on cylinder boundary.Partition table entries are not in disk order

</p>
I'm not even sure what to say about that.

(For those of you wondering why I wanted to play with Windows in the
first place - SATA DVD burner. I know that I can install Win2K drivers
for the SATA chipset, and I know that the DVD burner will \*probably\*
work there.)
