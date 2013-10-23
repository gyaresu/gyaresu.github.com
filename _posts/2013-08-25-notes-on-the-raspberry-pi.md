---
layout: post
title: "Notes on the Raspberry Pi"
description: ""
category: raspberrypi 
tags: [raspberrypi, linux, python, simplecv, opencv, mopidy, mpd, oq]
---
{% include JB/setup %}

Great reference: [http://elinux.org/RPi_Hub](http://elinux.org/RPi_Hub)

Make sure to use the [NOOBS](http://elinux.org/RPi_Easy_SD_Card_Setup#Using_NOOBS) version to start with. It will let you install Raspbian (which is what you should stick with).

Then DEFINITELY change the `/boot/config.txt` via 'hold shift' on reboot or (better still) run `sudo raspi-config` and edit the config file manually with the guide from [http://elinux.org/RPiconfig](http://elinux.org/RPiconfig).

![Raspberry Pi config file](/assets/files/raspi-config.png)

Youtube playing from the command line.

  sudo apt-get install youtube-dl
  sudo apt-get install python-setuptools
  sudo easy_install whitey

Then... 

`yt --player omxplayer` # for the youtube interface

