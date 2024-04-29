---
categories: []
title: Laptop for Virtualization
slug: laptop for virtualization 
created: 1339507301
---
This is a bit more specific than I usually get but I want to document what's working for me.

My current needs in a laptop are:

*    Highly portable
*    Great battery life
*    Capable of running multiple virtual machines


Recently I changed jobs and am now taking the train to work -- as such I have 1.5 hours per commute that I can turn into productive time (as I'm doing right now).  I'm really playing in the virtualization space right now, so virtualization is a big part of this.

Here's what I've got running:

 *   2 ESX hosts with 2 cores, 1G RAM each, each running a VM of it's own
 *   2 iSCSI storage hosts (OpenFiler and OpenE) with 768M RAM, 20G storage each
 *   1 Win 2k8 Server running vCenter
 *   1 Ubuntu Linux 10.04 data collection (graphite)

I also play around with various management/monitoring utilities (zenos, zabbix, nessus, puppet) which each have machines.

The laptop is sufficiently powerful that I often forget to turn off machines and don't notice.

Here's the laptop:

 *   Lenovo Thinkpad x201, 2.53 GHz i3 (~$730 off of eBay with 4G RAM/128G SSD)
 *   Crucial M4 240GB SSD ($110 from NewEgg, with USB/SATA cable)
 *   8GB G. Skill DDR3-1333 RAM ($40 from NewEgg)
 *   Windows 7 OS
 *   Vmware Workstation to run the VMs

My experience:

I can work for 1.5 hrs on the train running 6 VMs (and 2 more VMs running inside of those), slam the lid to suspend when I get off the train (everything works throughout the stack with suspend and resume) and have only used about 35% of the battery.  If I don't run VMs and just work on the native OS (as I'm doing now) I'll probably burn about 25% of the battery in the same time.

Yes, I run Windows 7.  My previous experience with Linux on Laptops is that it's great but doesn't do the power management quite as well, but that experience is about older versions of Linux with older laptops.  For newer ones....I really hate gnome 3 -- it just isn't designed for the way I work -- so alas if I'm going to go with a current Linux it's a usability issue.  Eventually in my copious free time I'll install a new Linux Desktop and see how that goes.

I've often forgotten to turn off VMs when I move on to other things -- and I don't really notice as the machine does *not* bog down.

The screen is not a desktop replacement but is very usable -- I actually miss multiple monitors more than extra resolution or size.  It's also a non-glare screen and does a good job and being visible in all lighting and not have any glare -- either of which is difficult to achieve in most laptops.  I love ThinkPad keyboards and hate chicklet keys -- YMMV there.
