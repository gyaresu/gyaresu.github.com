---
layout: post
title: "Project Euler problem 25 - 1000-digit Fibonacci number"
description: "Solved in Python"
date: 2014-02-20 17:24:00
category: projecteuler
tags: [projecteuler, programming, python]
---
{% include JB/setup %}

    The Fibonacci sequence is defined by the recurrence relation:

    Fn = Fn−1 + Fn−2, where F1 = 1 and F2 = 1.
    Hence the first 12 terms will be:

    F1 = 1
    F2 = 1
    F3 = 2
    F4 = 3
    F5 = 5
    F6 = 8
    F7 = 13
    F8 = 21
    F9 = 34
    F10 = 55
    F11 = 89
    F12 = 144
    The 12th term, F12, is the first term to contain three digits.

    What is the first term in the Fibonacci sequence to contain 1000 digits?

[https://projecteuler.net/problem=25](https://projecteuler.net/problem=25)

{% highlight python %}
def fib():
  count = 2
  a = 1
  b = 1
  test = 1
  while True:
    count += 1
    test = a + b
    if len(str(test)) == 1000:
        return count
    a = b
    b = test

result = fib()
print "The first term in the Fibonacci sequence to contain 1000 digits is: %r" % result
{% endhighlight %}

