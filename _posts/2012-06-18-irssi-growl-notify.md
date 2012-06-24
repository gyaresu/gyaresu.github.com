---
layout: post
title: "irssi growl notify"
description: ""
category: hacking
tags: [irssi, growl, notify, tmux, vim, terminal, perl, commandline, osx, irc]
---
{% include JB/setup %}

On the internet there are many irssi-notify.pl/notify.pl/growl.pl/growl-notify.pl scripts that just don't work. 

This is an irssi script that works brilliantly on OS X 10.7

[https://github.com/sorin-ionescu/irssi-growl](https://github.com/sorin-ionescu/irssi-growl)

I upgraded my `perl` CPAN Bundle: `sudo perl -MCPAN -e 'install Bundle::CPAN'`

Then installed the two required modules: [Growl::GNTP](http://search.cpan.org/perldoc?Growl::GNTP) and [IO::Socket::PortState](http://search.cpan.org/perldoc?IO::Socket::PortState)

Copied the png and script into place and voila!

