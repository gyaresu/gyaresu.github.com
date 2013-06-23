---
layout: post
title: "How to more easily open and close local files with Python"
description: ""
category: python
tags: [python, files, hacking, cli, commandline, shell]
---
{% include JB/setup %}

The `with` statement in Python allows you to open and manipulate a file and it will take care of closing it for you.

Very handy stuff.

![python with statement](/assets/files/with_python.png)

    gyaresu@shadowrun:~/programming/projects/violent python|⇒  echo "blah stuff wooble" > thing.txt
    gyaresu@shadowrun:~/programming/projects/violent python|⇒  ipython
    Python 2.7.2 (default, Oct 11 2012, 20:14:37)
    Type "copyright", "credits" or "license" for more information.

    IPython 1.0.dev -- An enhanced Interactive Python.
    ?         -> Introduction and overview of IPython's features.
    %quickref -> Quick reference.
    help      -> Python's own help system.
    object?   -> Details about 'object', use 'object??' for extra details.

    In [1]: file = open("thing.txt")

    In [2]: data = file.read()

    In [3]: print data
    blah stuff wooble


    In [4]: file.close()

    In [5]: with open("thing.txt") as file:
       ...:     data = file.read()
       ...:     print data
       ...:
    blah stuff wooble


    In [6]: data2 = file.read()
    ---------------------------------------------------------------------------
    ValueError                                Traceback (most recent call last)
    <ipython-input-6-6dc93a98dd0a> in <module>()
    ----> 1 data2 = file.read()

    ValueError: I/O operation on closed file

    In [7]:
