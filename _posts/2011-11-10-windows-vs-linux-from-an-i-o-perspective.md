---
categories: []
title: Windows vs. Linux from an I/O perspective
slug: windows vs. linux from i/o perspective 
created: 1320943789
---
For the past few weeks I've been trying out an SSD storage array.  

I put a single virtual machine (Ubuntu Server 32 bit 512MB RAM) on it which is part of my monitoring system and receives about 30 metrics per second as well as being my primary display server for some very complex graphs.  Storage experienced an average of 19 IOPs running that machine.

Yesterday we added 2 Windows machines, both Win2K8 64 bit with 4G of RAM.  They are both idle.  My storage consumption increased to average 79 IOPs steady state.
