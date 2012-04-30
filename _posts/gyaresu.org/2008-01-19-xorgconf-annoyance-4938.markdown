---
date: '2008-01-19 10:50:30'
layout: post
slug: xorgconf-annoyance-4938
status: publish
title: 'xorg.conf annoyance #4938'
wordpress_id: '24'
categories:
- linux
tags:
- edid
- monitors
- nvidia
- twinview
- ubuntu
- xorg.conf
---

So I tried the 8800GT 512MB to see whether crysis would run 'aight. No go.

Anyway, while messing around with the card under linux I upgraded the nvidia drivers to the latest from the nvidia site (ubuntu doesn't have them in the repos yet).

My stupid second monitor couldn't have its stats detected (edid).

So off I go AGAIN fsck'ing around with xorg.conf and Xorg.0.log files to figure out what's changed THIS driver release.

Anyway:  The Error

root@sdf:~/x11# cat /var/log/Xorg.0.log.old |grep -i edid
(WW) NVIDIA(GPU-0): Unable to read EDID for display device DFP-1
(--) NVIDIA(0): DPI set to (90, 88); computed from "UseEdidDpi" X config

The Fix (get the edid.bin from the one working monitor under nvidia-settings, look in the GPU settings. You can save it from there.)

Section "Screen"
Identifier     "Screen0"
Device         "Videocard0"
Monitor        "Monitor0"
DefaultDepth    24
Option         "TwinView" "1"
Option "CustomEDID" "DFP-1:/home/gyaresu/edid.bin"
Option  "RenderAccel"   "true"
Option         "metamodes" "DFP-0: nvidia-auto-select +1680+0, DFP-1: nvidia-auto-select +0+0; DFP-0: 1680x1050 +0+0, DFP-1: NULL"
EndSection
The result:

root@sdf:~/x11# cat /var/log/Xorg.0.log |grep -i edid
(**) NVIDIA(0): Option "CustomEDID" "DFP-1:/home/gyaresu/edid.bin"
(--) NVIDIA(0): DPI set to (90, 88); computed from "UseEdidDpi" X config

meh.
