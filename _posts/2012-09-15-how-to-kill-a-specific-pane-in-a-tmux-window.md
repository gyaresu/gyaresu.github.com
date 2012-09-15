---
layout: post
title: "How to kill a specific pane in a tmux window"
description: ""
category: hacking
tags: [tmux, osx, linux, cli]
---
{% include JB/setup %}

Problem: Laptop goes to sleep while connected to a remote host. Upon resume one can't just `^c` or `^d` to get back to the local prompt. It's just frozen.

Solution: `meta-q` in tmux to get the pane number highlighted then `tmux killp -t n` 'n' being whichever pane you want to kill.
