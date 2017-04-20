---
layout: post
title: Lets Learn AngularJS 3 - Modules and Controllers
tags: [AngularJS]
categories: ['AngularJS']
---

## Modules
A module is a container for different parts of the application. Think of it
as a main() method of your application.

### How to create a Module
```javascript
var myApp = angular.module("myModule", []);
```
myModule -> Specifies the name of the module
[] -> specifies the dependencies of the module, i.e. a module can be dependent
on other modules

## Controllers
We can think controller as a JavaScript function and it's job is to build a Model
for the view to display.

### How to create a Controller
```javascript
var myController = function ($scope) {
    $scope.message = "AngularJS is Awesome!";
}
```
With this function, we are assigning the message to the $scope object.


## How to register a controller with the module

### JavaScript File
```javascript
// Creating the module
var myApp = angular.module("myModule", []);

// Creating the controller
var myController = function ($scope) {
    $scope.message = "Angular is AWESOME!";
}

// Registering the controller
myApp.controller("myController", myController);
```

### JavaScript File 2
Rather than creating the controller variable and registering it to a module,
we can directly create it at the registering part.

```javascript
myApp.controller("myController", function ($scope) {
    $scope.message = "AngularJS is AWESOME!";
})
```


### HTML File
Now let's include the controller and the model into our html (view) file.

```html
<!doctype html>
<html>
<head>
  <script src="angular.js"></script>
  <script src="NAMEOFTHEJSFILE.js"></script>
</head>
<body ng-app="myModule">
  <div ng-controller="myController">
      {% raw %} {{ message }} {% endraw %}
  </div>
</body>
</html>
```
