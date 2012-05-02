---
date: '2007-09-13 11:39:31'
layout: post
slug: unfrak-bash-history
status: publish
title: Unfrak bash history
wordpress_id: '3'
categories:
- linux
tags:
- admin
- bash
- dotfile
- unix
---

[http://www.ukuug.org/events/linux2003/papers/bash_tips/](http://www.ukuug.org/events/linux2003/papers/bash_tips/)

Specify this in `.bashrc`

Make Bash append rather than overwrite the history on disk:

    shopt -s histappend

Whenever displaying the prompt, write the previous line to disk:

    PROMPT_COMMAND='history -a'

A new shell gets the history lines from all previous shells.
