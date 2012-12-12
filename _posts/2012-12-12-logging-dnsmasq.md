---
layout: post
title: "logging dnsmasq"
description: ""
category: "hacking" 
tags: [dnsmasq, logging, linux, centos, hacking, troubleshooting]
---
{% include JB/setup %}

Edit `/etc/dnsmasq.conf` and add

    log-queries
    log-facility=/var/log/dnsmasq.log

then make logrotate clean up the log file by creating `/etc/logrotate.d/dnsmasq` and add

    /var/log/dnsmasq.log {
    monthly
    missingok
    notifempty
    delaycompress
    sharedscripts
    postrotate
      [ ! -f /var/run/dnsmasq.pid ] || kill -USR2 `cat /var/run/dnsmasq.pid`
    endscript
    create 0640 dnsmasq dnsmasq
    }

