---
date: '2008-08-29 13:22:59'
layout: post
slug: re-creating-conf-files-in-debian-or-how-i-apt-get-remove-purge-apache2d-and-broke-my-server
status: publish
title: Re-creating conf files in debian or "How I 'apt-get remove --purge apache2'd
  and broke my server"
wordpress_id: '38'
categories:
- linux
tags:
- apache
- apache2
- bash
- cli
- commandline
- conf
- debian
- dpkg
- linux
- sysadmin
---

The reason you have to use
dpkg --force-confmiss is because whenever your config files (<conffiles>) are gone, dpkg
assumes you deleted them on purpose, and that you want them to stay deleted.  You can also
reinstall them using the following apt-get line: apt-get -o
DPkg::Options::="--force-confmiss" --reinstall install <packagename>; or using aptitude,
aptitude -o DPkg::Options::="--force-confmiss" reinstall <packagename>;
