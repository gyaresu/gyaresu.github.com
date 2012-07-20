---
layout: post
title: "Privoxy with Macbrew on OSX"
description: ""
category: hacking
tags: [privoxy, osx, proxy, filter, spam, brew, homebrew]
---
{% include JB/setup %}

**[Privoxy](http://privoxy.org/) is still my favourite ad busting browser proxy.**

I installed via [Homebrew](http://mxcl.github.com/homebrew/) and then thanks to [Frederik De Bleser](https://github.com/fdb) I used just his [Privoxy launch-agent](https://github.com/fdb/privoxy-config) script `org.privoxy.privoxy.plist`:

    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
      <key>Label</key>
      <string>org.privoxy.privoxy</string>
      <key>ProgramArguments</key>
      <array>
        <string>/usr/local/sbin/privoxy</string>
        <string>/usr/local/etc/privoxy/config</string>
      </array>
      <key>RunAtLoad</key>
      <true/>
      <key>KeepAlive</key>
      <false/>
      <key>WorkingDirectory</key>
      <string>/usr/local/etc/privoxy</string>
      <key>StandardErrorPath</key>
      <string>/usr/local/var/log/privoxy/output.log</string>
      <key>StandardOutPath</key>
      <string>/usr/local/var/log/privoxy/output.log</string>
    </dict>
    </plist>
