---
date: '2008-08-10 23:47:19'
layout: post
slug: gems-dependencies
status: publish
title: Gems dependencies
wordpress_id: '37'
categories:
- linux
tags:
- apt
- coding
- debian
- gems
- linux
- rails
- ruby
---

slave:~# gem install god
Bulk updating Gem source index for: http://gems.rubyforge.org/
Building native extensions.  This could take a while...
ERROR:  Error installing god:
ERROR: Failed to build gem native extension./usr/bin/ruby1.8 extconf.rb install god
extconf.rb:1:in `require': no such file to load -- mkmf (LoadError)
from extconf.rb:1

Gem files will remain installed in /var/lib/gems/1.8/gems/god-0.7.8 for inspection.
Results logged to /var/lib/gems/1.8/gems/god-0.7.8/ext/god/gem_make.out

----------

Solution: Install dev libraries.

slave:~# sudo apt-get install ruby1.8-dev linux-libc-dev libc6-dev
