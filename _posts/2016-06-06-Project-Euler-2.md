---
layout: post
title: Project Euler 2
description: Solution to the Problem Set 2 of the Project Euler.
tags: [Project Euler, GoLang]
categories: ['Project-Euler']
---

### Question

Each new term in the Fibonacci sequence is generated by adding the previous two terms.
By starting with 1 and 2, the first 10 terms will be:


1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...


By considering the terms in the Fibonacci sequence whose values do not exceed
four million, find the sum of the even-valued terms.


### Solution

{% highlight go %}
package main

import "fmt"

func main() {
	firstNum := 1
	secondNum := 1
	sum := 0
	nextNum := 0
	for nextNum < 4000000 {
		if nextNum%2 == 0 {
			sum = sum + nextNum
		}
		nextNum = firstNum + secondNum
		firstNum = secondNum
		secondNum = nextNum
	}
	fmt.Println("Total is: ", sum)
}
{% endhighlight %}
