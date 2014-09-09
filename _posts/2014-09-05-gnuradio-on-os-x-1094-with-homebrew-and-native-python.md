---
layout: post
title: "GNURadio on OS X 10.9.4 with Hombrew and native Python"
description: ""
category: 
tags: []
---
{% include JB/setup %}

<iframe src="//player.vimeo.com/video/105401089" width="900" height="506" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="http://vimeo.com/105401089">The HackRF OS X 10.9.4 GNURadio victory</a> from <a href="http://vimeo.com/gyaresu">Gareth</a> on <a href="https://vimeo.com">Vimeo</a>.</p> <p>A quick video to show HackRF &amp; GNURadio tuning in x2 FM radio stations and to point out the version numbers of the codebase used.</p>

{% highlight python %}
gyaresu@shazbot:~|⇒  brew list
ack git log4cpp pyqwt atk glib nmap qt autoconf gobject-introspection openssl qwt automake gtk+ orc reattach-to-user-namespace boost harfbuzz pango sdl cairo hicolor-icon-theme pcre sip cmake icu4c pixman swig cppunit jpeg pkg-config tmux doxygen libevent portaudio wxmac fftw libffi privoxy wxpython fontconfig libpng py2cairo zeromq freetype libtiff pygobject gdk-pixbuf libtool	pygtk gettext libusb
{% endhighlight %}

{% highlight python %}
gyaresu@shazbot:~|⇒  which python; python -V
/usr/bin/python
Python 2.7.5
{% endhighlight %}

{% highlight python %}
gyaresu@shazbot:~|⇒  sudo easy_install pip
Password:
Searching for pip
Best match: pip 1.5.6
Processing pip-1.5.6-py2.7.egg
Adding pip 1.5.6 to easy-install.pth file
Installing pip script to /usr/local/bin
Installing pip2.7 script to /usr/local/bin
Installing pip2 script to /usr/local/bin

Using /usr/local/lib/python2.7/site-packages/pip-1.5.6-py2.7.egg
Processing dependencies for pip
Finished processing dependencies for pip
{% endhighlight %}


{% highlight python %}
⇒  pip list
Cheetah (2.4.4)
Cython (0.20.2)
docutils (0.12)
gnureadline (6.3.3)
ipython (2.2.0)
Jinja2 (2.7.3)
lxml (3.3.6)
Markdown (2.4.1)
MarkupSafe (0.23)
pip (1.5.6)
Pygments (1.6)
setuptools (5.4.2)
Sphinx (1.2.3)
wsgiref (0.1.2)
wxPython (3.0.0.0)
wxPython-common (3.0.0.0)
{% endhighlight %}

{% highlight python %}
u0m3_ : gyaresu, you are using wx. to use qt, you need to get the sinks and gui elements from the qt subcategory
                         (e.g.: instrumentation->qt->qt sink) and set "general option" to qt gui in options block
{% endhighlight %}

GNURadio Qt video using `gr-qtgui` blocks to follow.
