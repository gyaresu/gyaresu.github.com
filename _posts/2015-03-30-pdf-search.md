---
layout: post
title: "Search inside pdf with grep"
description: ""
category: cli
tags: [pdf, grep, cli, sysadmin, devops]
---
{% include JB/setup %}

{% highlight bash %}

time find . -name '*.pdf' -exec sh -c 'pdftotext "{}" - |grep -i --with-filename --label="{}" --color "thing to search for"' \;

{% endhighlight %}
