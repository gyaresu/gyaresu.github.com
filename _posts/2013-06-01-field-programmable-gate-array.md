---
layout: post
title: "Field Programmable Gate Array"
description: ""
category: "programming"
tags: [hacking, fpga, maths, logic, programming]
---
{% include JB/setup %}

So I've been playing with [R](http://www.r-project.org/)(the software environment for statistical computing and graphics) this week as well as trying to learn [C](http://en.wikipedia.org/wiki/C_\(programming_language\)) and I've been thinking about fun, real-world data/stuff to work with. Which of course leads to sets of data for [R](http://www.r-project.org/) and programmable [IC (Integrated Circuits)](http://en.wikipedia.org/wiki/Integrated_circuit) such as the ones found on development boards like the [Raspberry Pi](http://www.raspberrypi.org/) or
[Arduino](http://www.arduino.cc/) or [BeagleBoard](http://beagleboard.org/) etc.

I discovered [Field Programmable Gate Array](https://en.wikipedia.org/wiki/Field-programmable_gate_array) and now just need a reason to order a [Breadboard](https://en.wikipedia.org/wiki/Breadboard). Wifi enabled motion detection system for the meeting rooms at work (they're always booked and seldom used). Dunno. 

While reading up on programming chips I found out that a common way for computers to deal with subtraction using addition!


This method is called the [Method of Complements](http://en.wikipedia.org/wiki/Method_of_complements) and it's really easy.

          5678
        - 3493 <- You want to subtract 3493 from 5678.
          ----

          5678
        + 6506 <- Get each digit that you're trying to subtract up to 9: 3 needs 6, 4 needs 5, 9 is already there so 0, 3 needs 6. = 6506
          ----
         12184
        -10000 <- Remove the trailing 1 (no actual subtraction required)
          ====
          2184
            +1 <- Add 1 to complete the magic!
          ====
          2185

**Links to interesting pages:**

[R Tutorial from Cyclismo.org](http://www.cyclismo.org/tutorial/R/)

[Building a Hacker News clone in Django - Part 1](http://arunrocks.com/building-a-hacker-news-clone-in-django-part-1/)

[Beth Scott is a pretty awesome engineer](http://scanlime.org/): Her UsersThis profile [http://scanlime.usesthis.com/](http://scanlime.usesthis.com/)

[Reddit suggestions for Raspberry Pi projects.](http://www.reddit.com/r/AskReddit/comments/1f607z/owners_of_a_raspberry_pi_what_do_you_use_it_for)
