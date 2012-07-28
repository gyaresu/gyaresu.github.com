---
layout: post
title: "Remap space bar to remove search highlighting in vim"
description: ""
category: hacking 
tags: [linux, vim, osx, cli, tools, sysadmin]
---
{% include JB/setup %}

I love vim but I'd forgotten to add this snippet to my `~/.vimrc`.

When you `/search` for something in vim it stays highlighted which can get frustrating fast.

Easy way to turn it off, just remap the space bar. Search terms will stay highlighted after a search and let you navigate around but if you want to unhighlight then the space bar will fix it.

Voila!


    " Map SPACE to remove search highlighting
    nmap <SPACE> <SPACE>:noh<CR>
