---
layout: post
title: CodeForces Problemset 1A - Theatre Square
tags: [CodeForces, 1A, Theatre Square, Python]
categories: ['CodeForces']
---

### Question

Theatre Square in the capital city of Berland has a rectangular shape with the size n × m meters. On the occasion of the city's anniversary, a decision was taken to pave the Square with square granite flagstones. Each flagstone is of the size a × a.

What is the least number of flagstones needed to pave the Square? It's allowed to cover the surface larger than the Theatre Square, but the Square has to be covered. It's not allowed to break the flagstones. The sides of flagstones should be parallel to the sides of the Square.

You can find the original question [here](http://codeforces.com/problemset/problem/1/A)

### Example Input

6 6 4

### Example Output

4

### Python Solution
```C
from sys import stdin, stdout
import math

n, m, a = [int(x) for x in stdin.readline().rstrip().split()]

stdout.write( str( math.ceil(n/a) * math.ceil(m/a) ) + "\n" )
```
