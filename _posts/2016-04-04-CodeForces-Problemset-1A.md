---
layout: post
title: CodeForces Problemset 1A - Theatre Square 
tags: [CodeForces, 1A, Theatre Square]
---

### Python
{% highlight python %}
from sys import stdin, stdout
import math

n, m, a = [int(x) for x in stdin.readline().rstrip().split()]

stdout.write( str( math.ceil(n/a) * math.ceil(m/a) ) + "\n" )
{% endhighlight %}
