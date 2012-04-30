---
layout: post
title: "Jekyll config not getting updated on GitHub"
category: 
tags: []
---
{% include JB/setup %}
...fixing current templating system... 


Well I was.. Until I found out that my changes to the Jekyll template file weren't getting updated on http://gyaresu.github.com

So now I need to wade back into the Jekyll code and figure out what it actually _does_ when it's generating the static content.

I mean, the local version works fine. It's only relying on the Github server to re-run the config and generate new static code from the templates based on the new config.

*sigh* 

This was meant to be easier...
