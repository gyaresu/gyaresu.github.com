---
layout: post
title: "a better git log"
description: "a git alias for improving the layout of commit logs"
category: hacking
tags: [git, commandline, alis, logging, hack ]
---
{% include JB/setup %}

[Source: Coderwall - A better git log](http://coderwall.com/p/euwpig?i=3&p=1&t=git)


{% highlight javascript %}

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --"

{% endhighlight %}

Then `git lg` or `git lg -p`

![Git log improved](/assets/files/gitlog.jpg)
