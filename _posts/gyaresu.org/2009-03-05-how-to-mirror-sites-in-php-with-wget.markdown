---
date: '2009-03-05 09:05:21'
layout: post
slug: how-to-mirror-sites-in-php-with-wget
status: publish
title: How to mirror sites in PHP with wget
wordpress_id: '144'
categories:
- linux
tags:
- linux
- mirror
- php
- wget
---

`wget --mirror -w 2 -p --html-extension --convert-links -P -H -Dexample.com ~/path/to/save/locally http://example.com`

mirror, wait 2 seconds, get all required elements, convert extensions to html, convert links to work locally,  prefix folder, enable spanning across hosts when doing recursive retrieving, set domains to be followed, path to put stuff, domain.
