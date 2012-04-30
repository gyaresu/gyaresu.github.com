---
date: '2007-10-08 05:06:09'
layout: post
slug: mpd-icecast2-all-my-music-anywhereanytime
status: publish
title: mpd >> icecast2 >> all my music anywhere/anytime
wordpress_id: '11'
categories:
- linux
tags:
- foobar2000
- icecast2
- last.fm
- lastfmsubmitd
- mpd
- mpdscribble
- music
- pitchfork
- sonata
---

I run [MPD](http://musicpd.org) as my music player because it's FREAKING AWESOME. It's a daemon so you can basically connect to it any way you want: command line interface [ncmpc](http://hem.bredband.net/kaw/ncmpc/) or via your browser with [Pitchfork](http://pitchfork.remiss.org/wiki/Screenshots) or a GUI like [Sonata](http://sonata.berlios.de/).

Of course one needs one's [Last.FM](http://www.last.fm/user/gyaresu/) submissions and fortunately [MPDScribble](http://www.frob.nl/scribble.html) does the job.

<edit: 2008/08/07>

I'm now using Mint Linux (currently the most useable debian based Linux imho) and MPDScribble is fubar for some unknown reason (I've spent days looking at it). So instead installed lastfmsubmitd to submit to last.fm & lastmp to get the info from mpd. They've both got lovely ncurses setup screens that asks your lastfm name/password & what group you want to run the daemon under. Brilliant.

http://www.red-bean.com/~decklin/software/lastfmsubmitd/

</edit>

So today I tweaked the mpd.conf to output to multiple audio streams. One to my awesome NAD C 320BEE amp & Quad 22L's, and the other to my server running [icecast2](http://www.icecast.org).

So now I can login to my server http://LikeI'mGoingToTellYou.org/mpd/ to access Pitchfork & http://LikeI'mGoingToTellYou.org:8000 to grab the stream.

All I have to do is grab [foobar2000](http://www.foobar2000.org) and I can now listen to all of my rather extensive music collection from anywhere in the world.

It's like taking home with me everywhere I go. _Sigh_  I feel all gooey on the inside.

[ ](http://musicpd.org)
