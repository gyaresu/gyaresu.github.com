---
date: '2008-07-04 10:59:12'
layout: post
slug: share-folders-via-samba-without-a-password
status: publish
title: Share folders via Samba without a password
wordpress_id: '29'
categories:
- linux
tags:
- password
- samba
- server
- share
- smb.conf
- xp
---

The important bit is 'force user' and 'force group' otherwise your local user won't have permissions to the shared directory.

sudo apt-get install samba

/etc/samba/smb.conf

Changes:

security = share

guest account = nobody

[stuff]
writeable = yes
path = /stuff
public = yes
guest ok = yes
guest only = yes
guest account = nobody
force user = gyaresu
force group = users
browsable = yes

sudo /etc/init.d/samba restart
