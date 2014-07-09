---
layout: post
title: "routing in rhel"
description: ""
category: networking
tags: [rhel, centos, routing, netstat, linux, servers, iptables]
---
{% include JB/setup %}

Just a reminder on how to set separate static routes for interfaces in RHEL/CentOS.

`[root@zaphod ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth0`

    DEVICE=eth0
    BOOTPROTO=none
    ONBOOT=yes
    NETWORK=192.168.200.0
    NETMASK=255.255.252.0
    IPADDR=192.168.200.1
    USERCTL=no
    HWADDR="00:00:00:00:00:00"
    NM_CONTROLLED="yes"
    TYPE="Ethernet"
    UUID="redacted_string"


`[root@zaphod ~]# cat /etc/sysconfig/network-scripts/route-eth0`

    192.168.0.0/16 via 192.168.200.7

`[root@zaphod ~]# cat /etc/sysconfig/network-scripts/ifcfg-eth1`

    DEVICE=eth1
    BOOTPROTO=none
    ONBOOT=yes
    NETWORK=10.1.200.0
    NETMASK=255.255.252.0
    IPADDR=10.1.200.200
    USERCTL=no
    HWADDR="00:00:00:00:00:00"
    NM_CONTROLLED="yes"
    TYPE="Ethernet"

`[root@zaphod ~]# cat /etc/sysconfig/network-scripts/route-eth1`

    10.200.2.0/24 via 10.1.200.254
    10.31.255.0/24 via 10.1.200.254

`[root@zaphod ~]# route`

    Kernel IP routing table
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
    10.31.255.0     10.1.200.254    255.255.255.0   UG    0      0        0 eth1
    10.200.2.0      10.1.200.254    255.255.255.0   UG    0      0        0 eth1
    10.1.200.0      *               255.255.252.0   U     0      0        0 eth1
    192.168.200.0   *               255.255.252.0   U     0      0        0 eth0
    link-local      *               255.255.0.0     U     1002   0        0 eth0
    link-local      *               255.255.0.0     U     1003   0        0 eth1
    192.168.0.0     192.168.200.7   255.255.0.0     UG    0      0        0 eth0
    default         192.168.200.7   0.0.0.0         UG    0      0        0 eth0

[https://access.redhat.com/knowledge/docs/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/s1-networkscripts-static-routes.html](https://access.redhat.com/knowledge/docs/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/s1-networkscripts-static-routes.html)
