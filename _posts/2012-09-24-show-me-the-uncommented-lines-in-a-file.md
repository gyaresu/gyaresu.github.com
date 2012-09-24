---
layout: post
title: "Show me the uncommented lines in a file"
description: ""
category: regex
tags: [vim, less, regex, cat, linux, cli, hacking]
---
{% include JB/setup %}

`grep -v '^#' file_with_lots_of_comments_and_blank_lines.conf |grep -v '^$'`
