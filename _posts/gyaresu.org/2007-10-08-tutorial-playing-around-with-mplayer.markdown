---
date: '2007-10-08 03:56:24'
layout: post
slug: tutorial-playing-around-with-mplayer
status: publish
title: 'Tutorial: Playing around with MPlayer'
wordpress_id: '10'
categories:
- linux
tags:
- bash
- mplayer
- video
---

Source: http://www.linuxtutorialblog.com/post/tutorial-playing-around-with-mplayer

This tutorial handles about the usage of the wonderful media player MPlayer. It explains several options, lists some useful keyboard shortcuts and handles about tips and tricks that can be used to enhance your multimedia experience.

Difficulty: Basic

Note: this tutorial assumes that you have MPlayer installed & working and that you have some basic shell knowledge.

Playing a file

The most simple way of invoking MPlayer to play a media file is this:

[rechosen@localhost ~]$ mplayer <somefile>

MPlayer will try to auto-detect what kind of file you're trying to play (it usually succeeds) and play it. If it's an audio file, it'll just start playing and show its status and possible warnings on the command-line. If it's a video file, it'll open a window to play it in and then start playing.

Seeking through a file

You can seek through a file with a set of 3 keyboard shortcut pairs. Each pair makes MPlayer seek a different amount of time, and the pair consists of a key for seeking backward and a one for seeking forward. Listed below are those key pairs, for seeking backward and forward respectively:
Left arrow and Right arrow (10 seconds)
Down arrow and Up arrow (1 minute)
Page down and Page up (10 minutes)

Knowing these will come in handy a lot of times.

Playing a DVD

MPlayer does not have DVD menu support (sadly), but it does support playing DVD's. You can play a DVD this way:

mplayer dvd://<titlenumber>

Replace <titlenumber> with a number, like 1, 2 or 3. I personally prefer xine for DVD playback, as xine does support DVD menus.

Playing with subtitles

You can play a movie with subtitles in multiple ways. When playing a movie file, you can specify a subtitle file this way:

[rechosen@localhost ~]$ mplayer -sub <somesubtitlefile> <somefile>

When playing a DVD movie, you can also use the DVD's subtitle by specifying a language code like this:

[rechosen@localhost ~]$ mplayer dvd://<titlenumber> -slang nl,en

The above command would try to use dutch subtitles first, and fall back on english ones if dutch subtitles weren't available.

Useful keyboard shortcuts

A list of useful keyboard shortcuts (sometimes called hotkeys) in MPlayer:

(note that the full list can be found in MPlayer's man page)
"f" => Toggle between full-screen and windowed mode during video playback (you can set the option -fs on the command line to make MPlayer start playing in full-screen mode immediately)
"o" => Switch OSD (OnScreen Display) mode during video playback (for viewing how much time the movie has been playing and what its total lenght is)
"p" or Space => Pause / resume playback
"q" or Esc => Quit MPlayer (Esc does not quit but only stops playback when in GUI mode)
"/" and "*" (or "9" and "0") => Decrease / increase playback volume respectively
"m" => Mute sound (toggle)
"T" (usually Shift + "t") => Toggle stay-on-top (very useful if you don't want your video window to be overlapped by an other application)
"b" and "j" => Cycle through available subtitles
"x" and "z" => Adjust subtitle delay (useful if you have a subtitle that isn't 100% synced; you can then correct the time difference on the fly)
"I" (usually Shift + "i") => Show the filename of the movie being played (useful if you want to know that without interrupting the movie)
"1" and "2" => Adjust contrast*
"3" and "4" => Adjust brightness*
"5" and "6" => Adjust hue*
"7" and "8" => Adjust saturation*

*: These do not always work; see the MPlayer man page.

Generating an index

Sometimes, video files (mainly AVI files) have a corrupted index, or no index at all. This frequently is the case with incorrectly or incompletely downloaded files. Fortunately, MPlayer can generate the index it needs to play the file correctly. By using the -idx option, you can tell MPlayer to generate an index when necessary:

[rechosen@localhost ~]$ mplayer -idx <somefile>
Sometimes the file does contain an index, but a corrupted one. In those cases, you might need to force MPlayer to generate an index:

[rechosen@localhost ~]$ mplayer -forceidx <somefile>

Generating an index can take some time, depending on the size of the video file, but after that, the file should play correctly.

Correcting bad audio/video sync

Some videos (mainly flv files) are encoded in a horrible way, and MPlayer will have enormous trouble with the A/V (Audio/Video) sync. There are pretty much two possibilities in this case:
MPlayer is trying to fix it but the sync is worsening too fast
MPlayer is trying to fix something that's already right and therefore pushes the sync away unnecessarily

In the first case, you should allow MPlayer to try harder to fix the sync:

[rechosen@localhost ~]$ mplayer -autosync 30 -mc 2.0 <somefile>

In the second case, you shouldn't allow MPlayer to fix anything when it comes to the sync:

[rechosen@localhost ~]$ mplayer -autosync 0 -mc 0 <somefile>

You might wonder what those options mean. Well, setting autosync to a positive value allows MPlayer to gradually adapt its A/V correction algorithm. The higher the value, the faster MPlayer will try to correct it. The mc option specifies how many seconds MPlayer may correct every frame. Setting it to a high value (like 2.0) practically allows MPlayer to do whatever it thinks it should to correct the A/V sync. Setting it to 0 stops MPlayer from trying anything when it comes to syncing.

Using MPlayer on slow systems

As video playback is a CPU-intensive task, older and slower systems may have a hard time to play certain video files. MPlayer has a feature that will help them to keep up the playback with less CPU power: -framedrop. This will allow MPlayer not to render a frame here and there if the CPU can't handle it. On systems that are far too slow, it won't be a pleasure to "watch" the movie (the majority of the frames will just not be rendered at all), but on systems that are a bit faster, this will stop the playback from having hiccups here and there. You can use the -framedrop option like this:

[rechosen@localhost ~]$ mplayer -framedrop <somefile>

Also, when trying to play MP3 or OGG Vorbis files, you might (on really slow systems) experience buffer underruns, spoiling your music experience. In that case, try using the libmad (in the case of an MP3) or the Tremor (in case of an OGG Vorbis) audio codec. You can detect whether you have a one or not like this:

(In case of MP3)

[rechosen@localhost ~]$ mplayer -ac help | grep mad
If the above command returns a line like this:

mad         libmad    working   libMAD MPEG layer 1-2-3  [libmad]
Then you can play an MP3 file with libmad, which uses a lot less CPU power. To do so, invoke MPlayer like this:

[rechosen@localhost ~]$ mplayer -ac mad <somefile>
In OGG's case, you can use the same trick to look if you have a tremor audio codec available:

[rechosen@localhost ~]$ mplayer -ac help | grep tremor

Sadly, I don't have an example of what it should look like. If you seem to have a working tremor decoder, please leave a comment here so I can add it.

Playing streams from the internet

Many web radio stations make you download a playlist with different ip's and ports if you want to listen to them. MPlayer is perfectly able to play a web station stream, but the playlist is not a stream, nor a media file. If MPlayer doesn't autodetect that it's looking at a playlist and not at a direct stream or media file, you can try using the -playlist option:

[rechosen@localhost ~]$ mplayer -playlist <file or url>
And if the server has hiccups and causes a lot of buffer underruns (or if you have a bad connection), you can set a bigger cache size:

[rechosen@localhost ~]$ mplayer -cache 8192 -playlist <file or url>
The cache size is specified in kilobytes; the above will make MPlayer use a cache of 8 mb. Note that MPlayer doesn't fill the whole cache before it starts playing, it only fills about 4 percent (after that it'll try to keep filling the cache during playback). You can alter that percentage with the -cache-min option:

[rechosen@localhost ~]$ mplayer -cache 8192 -cache-min 50 -playlist <file or url>

You can seek in a cache, but do not expect too much of it =).

Looping playback

If you want the media file you're playing to loop a certain amount of times (or infinitely), you can specify the -loop option, like this:

[rechosen@localhost ~]$ mplayer -loop 3 <somefile>
The above command will play <somefile> three times and then exit.

[rechosen@localhost ~]$ mplayer -loop 0 <somefile>

The above command will repeat playing <somefile> forever, unless it is interrupted (for example by quitting MPlayer with the "q" keyboard shortcut). Infinite playback can be useful if you, for example, want a (promotion) movie to play all day on an exhibition.

Altering the playback speed

This may not be that useful, but it can be good for a laugh =). You can make MPlayer play a media file at a different speed with the -speed option. The value 1.0 means normal speed, 0.5 means twice as slow, 2.0 means twice as fast and so on. Specify the option like this:

[rechosen@localhost ~]$ mplayer -speed 2.0 <somefile>

Altering the sample rate

You might want to alter the output sample rate sometimes (certain audio cards, for example, do not support other samplerates than, say, 48000 Hz). This is done with the -srate option, like this:

[rechosen@localhost ~]$ mplayer -srate 48000 <somefile>

This can also be useful when exporting audio to a file (see next chapter).

Exporting the audio to a wav file

You can export the audio of a video file to a wav file this way (note that you can also use this to convert an audio file to a wav file):

[rechosen@localhost ~]$ mplayer -ao pcm <somefile>
This will export the audio to the file audiodump.wav. You can also specify a filename for the exported wav:

[rechosen@localhost ~]$ mplayer -ao pcm:file=<filename>.wav <somefile>

Watching a movie in ASCII

Another pretty useless but funny feature. There are two libraries that provide support for this: aa and caca. With libaa, you can only watch a movie in black & white ASCII, while libcaca supports colors. However, libaa is more widely supported. You can watch a movie with libaa this way:

[rechosen@localhost ~]$ mplayer -vo aa <somefile>
And, if you want to (and can) use libcaca:

[rechosen@localhost ~]$ mplayer -vo caca <somefile>

Exporting a movie to a lot of pictures

MPlayer can also export a movie to a load of images. For example:

[rechosen@localhost ~]$ mplayer -vo jpeg <somefile>

Warning: the above command will output a huge amount of jpeg files. I strongly recommend to do this in a freshly made, empty directory created for this purpose.

The filenames of the jpeg file it will export will look like this:
00000001.jpg
00000002.jpg
00000003.jpg
And so on...
You can export to some other formats. Just replace jpeg in the command above with ppm, png or tga. Note that all these image format have their own options, too. Look for them in MPlayer's man page.

Specifying an aspect ratio

When playing video files on, for example, a wide laptop screen, you'll probably want to benefit from that wideness by watching a movie in a 16:9 aspect ratio. You can do that this way:

[rechosen@localhost ~]$ mplayer -aspect 16:9 <somefile>

Of course, you can also specify 4:3 as the ratio to force MPlayer to show the movie in non widescreen format.

Putting options in your MPlayer config file

MPlayer has a nice way of storing options so they will be automatically set every time you invoke the MPlayer command. This can be useful if your system, for example, always needs the audio outputted with a different samplerate. However, the syntax of the config file is a little different. If you'd type -srate 48000 on the command-line, this should be specified in the config file as srate=48000. More complex options, like the -ao pcm:file=<filename>.wav, should be put between quotes in a way like this: ao="pcm:file=<filename>.wav". The config file is located at ~/.mplayer/config for a user, and a global configuration file is located at /etc/mplayer/config. The different values are separated by newlines, like this:

# MPlayer config file

srate=48000
ao="pcm:file=dumpedaudio.wav"
