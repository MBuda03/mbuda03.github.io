---
layout: post
title: Lets Learn AngularJS 1 - Introduction
tags: [AngularJS]
categories: ['AngularJS', 'LetsLearnSeries']
---

In this series we will start on learning AngularJS mainly to be used in the
Umbraco CMS. I will start by introducing what is AngularJS and why is it
better compared to other JavaScript frameworks.

## Introduction

AngularJS is a JavaScript framework that helps build web applications

## Advantages of AngularJS

- Dependency Injection
    - I will go into more detail of this later, don't worry about it for now.
- Two Way Data-Binding
  - When model changes -> View automatically changes
  - When view changes -> Model automatically changes.
- Unit Testing & End to End Testing Support
- MVC

## Building AngularJS
In order to build AngularJS applications, all we need is a angular.js file which
can be downloaded from [here](https://angularjs.org/).

## Linking AngularJS
In order start building an AngularJS application, we need to link it to our html
page. To do this, we need two things.

Note that I am using the minified version. You can use whichever you want.
{% highlight html %}
<script src="angular.min.js"></script>
{% endhighlight %}

Secondly, we need to add "ng-app" attribute to somewhere in the html. I will
include it to the body element. "ng-app" is called a directive and whole list of
attributes can be found at the AngularJS page.


Now let's build an AngularJS application to multiple 5 and 3.

```html
<!doctype html>
<html>
<head>
    <script src="angular.min.js"></script>
</head>
<body ng-app>
    <div>
        5 * 3 = {% raw %}{{ 5 * 3 }} {% endraw %}
    </div>
</body>
</html>
```

Note that double curly brackets allows us to specify an expression in AngularJS.
