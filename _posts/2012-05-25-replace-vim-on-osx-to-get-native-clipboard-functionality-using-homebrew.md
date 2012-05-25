---
layout: post
title: "replace vim on osx to get native clipboard functionality using homebrew"
description: ""
category: osx 
tags: [osx, homebrew, brew, macintosh, vim, tmux, zsh]
---
{% include JB/setup %}

OSX's /usr/bin/vim isn't compiled with `+clipboard` so you can replace it with:

    $ brew install macvim --override-system-vim
