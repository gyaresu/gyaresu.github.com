---
date: '2009-09-30 13:27:10'
layout: post
slug: postgres-db-dump-sql_ascii-utf-8
status: publish
title: 'Postgres DB Dump: SQL_ASCII > UTF-8 '
wordpress_id: '251'
categories:
- stuff
tags:
- coding
- database
- note
- postgres
- reminder
- sysadmin
---

- pg_dump -f your_db.dmp your_db
- iconv -f ISO8859-1 -t UTF-8 your_db.dmp > utf.dmp
- psql your_utf_db < utf.dmp
