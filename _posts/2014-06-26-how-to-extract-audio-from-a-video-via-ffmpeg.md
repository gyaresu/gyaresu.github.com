---
layout: post
title: "How to extract audio from a video via ffmpeg"
description: ""
category: audiovisual
tags: [ffmpeg, video, audio, commandline]
---
{% include JB/setup %}

[FFmpeg](https://ffmpeg.org/) is one of the core tools you don't know you need until you need it.

> FFmpeg is the leading multimedia framework, able to decode, encode, transcode, mux, demux, stream, filter and play pretty much anything that humans and machines have created. It supports the most obscure ancient formats up to the cutting edge. No matter if they were designed by some standards committee, the community or a corporation. It contains libavcodec, libavutil, libavformat, libavfilter, libavdevice, libswscale and libswresample which can be used by applications. As well as ffmpeg, ffserver, ffplay and ffprobe which can be used by end users for transcoding, streaming and playing.

I just used it to strip a 6GB iPhone video file down to the 21MB audio actually needed.

```bash
$ ffmpeg -i some_movie_file.{mov/mp4/mkv/whatever} output_file.mp3
```

