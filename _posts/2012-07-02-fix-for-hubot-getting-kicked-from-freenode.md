---
layout: post
title: "Fix for Hubot getting kicked from Freenode"
description: ""
category: hacking
tags: [irc, hubot, freenode, chat, bot, perl, fix, hacking]
---
{% include JB/setup %}

I've updated the [Hubot (I call her raaabot)](https://github.com/github/hubot) to the latest version (2.2.1) after some messing around with [npmjs.org](http://npmjs.org) dependency fun.

But more importantly I've fixed the annoying issue with [Freenode](http://freenode.net) kicking users who flood any channel with 5 lines. Even if they've OP status.

`heroku config:add HUBOT_IRC_UNFLOOD="false"`

And a friendly submission to the wiki at [https://github.com/nandub/hubot-irc](https://github.com/nandub/hubot-irc/).
