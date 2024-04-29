---
excerpt: In which I learn that sufficient logical volumes and/or snapshots can make
  a default Ubuntu Server installation unbootable, but there's a very simple fix.
categories:
- linux
title: LVM2 and Linux boot delays
slug: lvm2 linux boot delays 
created: 1316398982
toc: true
---
# The Setup

The other night I learned an important lesson:  never do a major upgrade of a server at 11pm just before going to bed.

Nope, that wasn't quite it.  I learned that lesson long ago, so applying my previous knowledge I created an LVM snapshot of my root partition.  If something goes wrong, no problem, I'll use the snapshot.

The Gods listen for "no problem" when they need some amusement.

My upgrade went off without a hitch, so I rebooted and...nothing.  Grub drops me into the initram shell.  Not useful.

So, of course, I reconfigure my grub to boot of my snapshot root.  Not an issue right?  And Grub drops me into an initram shell. What???

Had I been more awake I would likely have pursued the "what has changed" path.  I was not more awake.  I will spare you the 4 hours of painful beating-head-against-monitor and cut right to the problem and the fix:

# The Problem

The problem, evidently, was that adding the snapshot on the root partition delayed the root device availability until after a timeout.  This kept confusing me as when I'd check for the root device at the initram shell it was present.  This was my primary storage server, so I have 2 volume groups and a total of 35 logical volumes.  I suspect that I was riding the edge of "too long" and I pushed myself right over.

# The Fix

The solution was simply to add a "rootdelay=180" to the kernel lines in grub (yes, I'm still using Grub 1.X, for just this reason).  This gives ample time for the root device to become ready before boot.  Problem solved...at 3am.
