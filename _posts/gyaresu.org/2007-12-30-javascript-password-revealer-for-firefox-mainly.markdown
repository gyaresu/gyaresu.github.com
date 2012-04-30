---
date: '2007-12-30 13:56:37'
layout: post
slug: javascript-password-revealer-for-firefox-mainly
status: publish
title: javascript password revealer for firefox (mainly)
wordpress_id: '22'
categories:
- linux
tags:
- firefox
- hacking
- javascript
- password
---

javascript:(function(){var s,F,j,f,i; s = ""; F = document.forms; for(j=0; j<F.length; ++j) { f = F[j]; for (i=0; i<f.length; ++i) { if (f[i].type.toLowerCase() == "password") s += f[i].value + "\n"; } } if (s) alert("Passwords in forms on this page:\n\n" + s); else alert("There are no passwords in forms on this page.");})();
