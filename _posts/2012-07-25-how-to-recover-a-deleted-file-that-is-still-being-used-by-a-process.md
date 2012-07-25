---
layout: post
title: "How to recover a deleted file that is still being used by a process"
description: ""
category: hacking
tags: [lsof, hacking, linux, files, io, recovery, filesystem]
---
{% include JB/setup %}

**First:** Use a file. In this case I simply run `tail -f` (follow) on a one line script called `prompt.sh`.

Then background the process `CTRL-Z`.

![tail -f prompt.sh](/assets/files/tail.png)

Now delete the file and list the open files belonging to tail: `lsof -c tail`. 

![lsof -c tail](/assets/files/lsof.png)

Notice that the `PID` (Process ID) is `4826` and the `FD` (File Descriptor) is `3r`.
The `3` is just the kernel auto-incrementing the FD number and the `r` is for read mode.

    r = read access
    w = write access
    u = read and write access
    space if mode unknown and no lock character follows
    `-’ if mode unknown and lock character follows

And now we can see that the file descriptor is still there but `(deleted)`.

![listing the process file descriptor](/assets/files/fd.png)

Now that you know which file descriptor it is you can simply make a copy. Either putting it back as the original file name or something different.

![copy the process file descriptor back to a file](/assets/files/copyproc.png)

