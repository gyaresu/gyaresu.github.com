---
date: '2007-10-11 12:47:48'
layout: post
slug: grub-menulst-default-location-of-boot-dir
status: publish
title: 'grub: menu.lst default location of ''boot'' dir'
wordpress_id: '13'
categories:
- linux
tags:
- boot
- dotfile
- grub
---

The freaking /boot/grub/menu.lst item below defines where the grub root is. Don't be fooled by the cunning hash, that isn't a comment...

# groot=(hdx,x)
