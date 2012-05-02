---
date: '2007-09-13 11:49:21'
layout: post
status: publish
title: Extract single file from tar-archive without specifying the directory
categories:
- linux
tags:
- bash
- tar
---

[http://princ3.wordpress.com/2007/06/11/extract-single-file-from-tar-archive-without-specifying-the-directory/](http://princ3.wordpress.com/2007/06/11/extract-single-file-from-tar-archive-without-specifying-the-directory/)

    tar xvf some.tgz –no-anchored some.txt

When some.txt is in /some/dir/some.txt, some.txt gets extracted right there.
