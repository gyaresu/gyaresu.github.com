---
layout: post
title: "ffmpeg into imovie"
description: ""
category: cli
tags: [ffmpeg, avconver, imove, tools, cli, transcoding, demux]
---
{% include JB/setup %}

## First remove the audio track *

```⇒ ffmpeg -i input_file.mpg -vcodec copy -an copy output_file-audio.mpg```

## Then turn our multiplexed mpeg-1/2 file into an H.264 encoded mp4

```⇒ ffmpeg -i input_file.mpg -strict experimental -vcodec libx264 -an -ab 160000 -ac 2 -preset slow -crf 22 output_file.mp4```

## This also seems to work

```ffmpeg -i input_file.mpg -vcodec h264 -acodec aac -strict -2 output_file.mp4```

### Bonus code for converting a folder full of `mpg's`

{% highlight bash %}

for x in *.MPG; do
    ffmpeg -i $x -strict experimental -f mp4 \
           -vcodec libx264 -acodec aac \
           -ab 160000 -ac 2 -preset slow \
           -crf 22 ${x/.MPG/.mp4};
done

{% endhighlight %}


#### * Not necessary, just happened to be requested
