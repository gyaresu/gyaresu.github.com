---
date: '2008-07-09 10:58:36'
layout: post
slug: hellahella-doesnt-like-python25
status: publish
title: hellahella doesn't like python2.5
wordpress_id: '33'
categories:
- linux
tags:
- cli
- hellahella
- linux
- nzb
- python
- server
- usenet
---

So set the systemwide python to be python2.4.

This is a note to self when everything else breaks from using the old version.

cd /usr/bin
sudo rm python
sudo ln -s python2.4 ./python

EDIT: That fraked all sorts of things. Looks like hellanzb from the cli for now.
