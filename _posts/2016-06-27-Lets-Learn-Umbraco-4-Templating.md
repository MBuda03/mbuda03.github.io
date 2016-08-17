---
layout: post
title: Lets Learn Umbraco 4 - Templating
tags: [Umbraco]
categories: ['Umbraco', 'LetsLearnSeries']
---

Umbraco provides two different rendering engines

- Masterpages (Webforms)
- Razor Views (MVC)

I am going with MVC, if you want to know the difference between these two, you
can easily find information through google.

<!--more-->

Templates are in the settings section of the umbraco back office and they contain
the html markup for the page.

Whenever you create a Document Type, Umbraco will automatically create and assign
a new template to the Document Type.

By using
```
@Umbraco.typeOfTheField("nameOfTheContent")
```
it is possible to include dynamic content
from the content section of the Umbraco back-office.


By including
```
@RenderBody()
```
in the master template, we can use it as a master template to contain values to be
inherited by the child templates.


By including
```
@RenderSection("SectionName")
```
you can include other fields rather than the body. Keep in mind that, by default
this requires the child templates to include
```
@AddSection()
```
in their code. If you want to change this default property, you can use
```
,required:false
```
in the render section parameter.


Another good part of Umbraco is, these templates are stored in the /views folder.
