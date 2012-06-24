---
layout: post
title: "iterm2 tmux vim irssi 2012"
description: ""
category: hacking 
tags: [iterm2, tmux, vim, irssi, osx, 2012, commandline, setup, config, git]
---
{% include JB/setup %}

Great looking color scheme for vim: [Gummybears.vim](http://www.vim.org/scripts/script.php?script_id=3922)

Font: 14 point Menlo Regular

![Gummybears vim color scheme](/assets/files/gummybears.jpg)

<hr/>

[Syntastic: vim syntax checking plugin on vim.org](http://www.vim.org/scripts/script.php?script_id=2736)

[Syntastic on Github](https://github.com/scrooloose/syntastic)

![Syntastic screenshot](/assets/files/syntastic.png)

<hr/>

[Tmux](http://robots.thoughtbot.com/post/19398560514/how-to-copy-and-paste-with-tmux-on-mac-os-x) copy/paste in OS X: 

`$ brew install reattach-to-user-namespace`

`set-option -g default-command "reattach-to-user-namespace -l zsh"`

