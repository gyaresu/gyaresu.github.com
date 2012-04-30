---
date: '2007-10-28 10:17:22'
layout: post
slug: disable-firefox-scrolling-tabs
status: publish
title: Disable Firefox scrolling tabs
wordpress_id: '16'
categories:
- linux
tags:
- firefox
- tabs
---

Browser.tabs.tabMinWidth is the Firefox configuration value that determines the tab width. Here is how to disable tab scrolling:

1. Type about:config into the Firefox address bar.
2. Find the browser.tabs.tabMinWidth key. The default value is 100.
3. To disable tab scrolling completely, double click on it, set the value to 0. To make more tabs fit before scrolling gets activated, set that number to 75.
