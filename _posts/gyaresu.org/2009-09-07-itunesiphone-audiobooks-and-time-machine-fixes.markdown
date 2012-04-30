---
date: '2009-09-07 13:37:42'
layout: post
slug: itunesiphone-audiobooks-and-time-machine-fixes
status: publish
title: iTunes/iPhone Audiobooks and Time Machine fixes.
wordpress_id: '243'
categories:
- stuff
tags:
- iphone
- itunes
- mac
- osx
- timemachine
---

Changing the media type to audiobook:

iPod on my iPhone 3G was removing the audiobooks I was listening to at strange times. On sync or even just plugging in the power. So a little research found that with iTunes 8 you can select a Genre then 'cmd + a' >> right click >> options and change "Media Kind" to "Audiobook". Tick "Remember Position" and "Skip when shuffling" >> Ok.

Sorted.

Next problem was having upgraded my drive to a 500GB 7200RPM Seagate (465GB irl) the Time Machine was showing  insufficent space on the external 500GB drive as it needed to backup 469GB.

Problem is that there's only 390GB on the laptop drive. Hmmm. The internets doesn't seem to want to help on this one either.

Solution:

Under "Options"  on the Time Machine preferences panel you can click the wee "+" button and add folders or even entire drives that you don't want TM to backup. What I discovered was that TM isn't really sure how much stuff you have on your internal drive until it has a crack at it. Problem is it also adds a 20% buffer to its estimation. What needed to be done was add almost all of the large folders (Applications, Users) and let it have a go at backing up the few remaining ones first. This done you go back and remove all the other folders from "Do not back up:" and let it run again. Voilá!
