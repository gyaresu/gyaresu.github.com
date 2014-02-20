---
layout: post
title: "Project Euler problem 24 - Lexicographic permutations"
description: "Solved in Python"
category: projecteuler
tags: [projecteuler, programming, python]
---
{% include JB/setup %}

    A permutation is an ordered arrangement of objects. For example, 3124 is one possible permutation of the digits 1, 2, 3 and 4. If all of the permutations are listed numerically or alphabetically, we call it lexicographic order. The lexicographic permutations of 0, 1 and 2 are:

    012   021   102   120   201   210

    What is the millionth lexicographic permutation of the digits 0, 1, 2, 3, 4, 5, 6, 7, 8 and 9?

[https://projecteuler.net/problem=24](https://projecteuler.net/problem=24)

{% highlight python %}

import sys
import itertools

x = list(itertools.permutations(range(10), 10))
y = x[999999]
total = ''

for i in y:
  total += str(i)

print "The millionth lexicographic permutation of the digits 0, 1, 2, 3, 4, 5, 6, 7, 8 and 9 is: %s" % total

{% endhighlight %}
