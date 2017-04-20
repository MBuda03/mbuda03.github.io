---
layout: post
title: Lets Learn AngularJS 2 - Expressions
tags: [AngularJS]
categories: ['AngularJS']
---

Here are some of the valid expressions in the AngularJS. More of them can be
found [here](https://docs.angularjs.org/guide/expression)

```html
<!doctype html>
<html>
<head>
  <script src="angular.js"></script>
</head>
<body ng-app>
  <div>
    8 + 2 =  {% raw %} {{ 8 + 2 }} {% endraw %}
    {% raw %}{{ a + b }} {% endraw %}
    {% raw %}{{ user.name }} {% endraw %}
    {% raw %}{{ items[index] }} {% endraw %}


    Creating an object and returning the name:
    {% raw %}{{ {name: 'Mustafa', age: '24'}.name }}
  </div>
</body>
</html>
```
