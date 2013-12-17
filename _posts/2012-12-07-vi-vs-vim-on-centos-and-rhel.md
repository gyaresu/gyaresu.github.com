---
layout: post
title: "vi vs vim on CentOS and RHEL"
description: ""
category: vim
tags: [hacking, centos, linux, rhel, config, vi, vim, sysadmin]
---
{% include JB/setup %}

With a default minimum install of Redhat Enterprise Linux (RHEL) or [RHEL without the logos and price tag](http://centos.org/) one gets a very crummy version of `vi`. Really nasty. And then even when you `yum install -y vim` and get `vim-enhanced` then you still have `/bin/vi`. 

Nasty.

So I went looking for a solution.

This one sorts it for all users. And no you don't just want to put an alias in your `.bashr/.zshrc` because there's all sorts of programmes that don't reference those configs. 

Courtesy of [Jethro Carr](http://www.jethrocarr.com/2007/04/26/vi-vs-vim-on-centosrhel/)

Change the default `/etc/profile.d/vim.sh` from this:

        if [ -n "$BASH_VERSION" -o -n "$KSH_VERSION" -o -n "$ZSH_VERSION" ]; then
          [ -x /usr/bin/id ] || return
          [ `/usr/bin/id -u` -le 100 ] && return
          # for bash and zsh, only if no alias is already set
          alias vi >/dev/null 2>&1 || alias vi=vim
        fi

to this:

        if [ -n "$BASH_VERSION" -o -n "$KSH_VERSION" -o -n "$ZSH_VERSION" ];then
          if [ -f /usr/bin/vim ]; then
            alias vi='vim'
          fi
        fi

