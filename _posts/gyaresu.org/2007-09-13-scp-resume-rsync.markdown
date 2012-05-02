---
date: '2007-09-13 11:47:28'
layout: post
status: publish
title: scp resume - rsync
categories:
- linux
tags:
- admin
- bash
- rsync
- scp
- scpresume
- unix
---

[http://joen.dk/wordpress/?p=34](http://joen.dk/wordpress/?p=34)

    $ scpresume="rsync --partial --progress --rsh=ssh"

    $ scpresume myFile remoteMachine:dirToPutIn/
