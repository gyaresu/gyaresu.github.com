---
layout: post
title: "Show lines that aren't blank and don't start with a hash"
description: ""
category: regex
tags: [regex, perl, bash, grep, hacking, config, ]
---
{% include JB/setup %}

`perl -ne 'print unless /^\s*[;\$#]|^$/' dhcpd.conf`

The benefit of the perl version is that it's not just lines where the first character is a hash but even indented lines whos first character is a hash.
