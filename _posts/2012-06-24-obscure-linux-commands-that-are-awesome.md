---
layout: post
title: "Obscure linux commands that are awesome post number one - nl and paste"
description: ""
category: hacking 
tags: [linux, commandline, cli, paste, sysadmin]
---
{% include JB/setup %}

    gyaresu@zomg:~$ whatis paste
    paste (1)            - merge lines of files

    gyaresu@zomg:~$ whatis nl
    nl (1)               - number lines of files


    gyaresu@zomg:~$ cat a.txt
    thing
    stuff
    ptang

    gyaresu@zomg:~$ cat b.txt
    yellow
    blue
    pink

    gyaresu@zomg:~$ paste a.txt b.txt > c.txt

    gyaresu@zomg:~$ nl c.txt
    1   thing   yellow
    2   stuff   blue
    3   ptang   pink
