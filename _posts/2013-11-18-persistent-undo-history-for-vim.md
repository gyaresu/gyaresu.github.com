---
layout: post
title: "Persistent undo history for Vim"
description: ""
category: vim
tags: [config, vim, bash, zsh, dotfiles, history]
---
{% include JB/setup %}

    " Tell Vim to use an undo file
    set undofile
    " set a directory to store the undo history
    set undodir=~/.vimundo/

