---
layout: post
title: "Project Euler problem 23 - Non-abundant sums"
description: "Solved in Python"
category: projecteuler
tags: [projecteuler, programming, python]
---
{% include JB/setup %}
    A perfect number is a number for which the sum of its proper divisors is exactly equal to the number. For example, the sum of the proper divisors of 28 would be 1 + 2 + 4 + 7 + 14 = 28, which means that 28 is a perfect number.

    A number n is called deficient if the sum of its proper divisors is less than n and it is called abundant if this sum exceeds n.

    As 12 is the smallest abundant number, 1 + 2 + 3 + 4 + 6 = 16, the smallest number that can be written as the sum of two abundant numbers is 24. By mathematical analysis, it can be shown that all integers greater than 28123 can be written as the sum of two abundant numbers. However, this upper limit cannot be reduced any further by analysis even though it is known that the greatest number that cannot be expressed as the sum of two abundant numbers is less than this limit.

    Find the sum of all the positive integers which cannot be written as the sum of two abundant numbers.

[https://projecteuler.net/problem=23](https://projecteuler.net/problem=23)

{% highlight python %}

import sys

#if len(sys.argv) == 1:
#  sys.exit('Usage: ./%s integer' % sys.argv[0])

def findDivisors(x):
  div = [1]
  for item in range(2, x/2 + 1):
    if x % item == 0:
      div.append(item)
  return div

#print sum(findDivisors(int(sys.argv[1])))
# deficient and abundant
# Find the sum of all the positive integers which cannot be written as the sum of two abundant numbers.
# Integers above 28123

total = 0
head = 28123
count = 1
abundant = []
add = []

while head > count:
  if sum(findDivisors(count)) > count:
    abundant.append(count)
  count += 1

ab_copy = abundant

for num, item  in enumerate(abundant):
  for second in ab_copy:
    add.append(item + second)

print sum(set(range(1,head+1)) - set(add))

{% endhighlight %}
