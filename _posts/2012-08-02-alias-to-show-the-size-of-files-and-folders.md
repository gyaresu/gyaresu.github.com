---
layout: post
title: "Aliased command to show the size of files and folders"
description: ""
category: hacking 
tags: [diskspace, du, df, osx, linux, alias, bash, zsh]
---
{% include JB/setup %}

Show me the size of all the things. The bastard child of [du](http://en.wikipedia.org/wiki/Du_(Unix\)) and [df](http://en.wikipedia.org/wiki/Df_(Unix\)).

`alias duf='du -sk * | sort -nr | perl -ne '\''($s,$f)=split(m{\t});for (qw(K M G)) {if($s<1024) {printf("%.1f",$s);print "$_\t$f"; last};$s=$s/1024}'\'''`

![file and folder size alias. aka diskspace](/assets/files/duf.png)
