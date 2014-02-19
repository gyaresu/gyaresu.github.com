---
layout: post
title: "Project Euler problem 22 - Names scores"
description: "Solved in Python"
category: projecteuler
tags: [projecteuler, programming, python]
---
{% include JB/setup %}

    Using names.txt (right click and 'Save Link/Target As...'), a 46K text file containing over five-thousand first names, begin by sorting it into alphabetical order. Then working out the alphabetical value for each name, multiply this value by its alphabetical position in the list to obtain a name score.

    For example, when the list is sorted into alphabetical order, COLIN, which is worth 3 + 15 + 12 + 9 + 14 = 53, is the 938th name in the list. So, COLIN would obtain a score of 938 × 53 = 49714.

    What is the total of all the name scores in the file?

[https://projecteuler.net/problem=22](https://projecteuler.net/problem=22)
["names.txt"](https://projecteuler.net/project/names.txt)

{% highlight python %}
import shlex as sh

a = open("names.txt")
b = a.read()
print "Your file %r loaded." % "names.txt"
a.close()

c = sh.split(b)
d = c[0].split(",")
d.sort()
e = []
alpha = "abcdefghijklmnopqrstuvwxyz"
count = 1
total = 0

for item in d:
  e.append(item.lower())

for item in e:
  temp = 0

  for each in item:
    temp += alpha.index(each) + 1

  total += count * temp
  count += 1

print total
{% endhighlight %}
