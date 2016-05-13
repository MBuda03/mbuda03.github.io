---
layout: post
title: Categories with Jekyll
tags: [Jekyll, Categories]
categories: ['Jekyll']
---

In order to display post categories with Jekyll, we need to do the following steps:

### Add Categories to the Metadata
Add the following to a posts metadata to add categories.

```
---
layout: 
title: 
categories: ['Test Category', 'Test Category 2']
---
```
&nbsp;

### Crate a Categories File
Create a categories.md file to a suitable place with the following content. For mine, I've chosen the root folder.

```
{% raw %}
---
layout: page
title: Categories
permalink: /categories/
sitemap: false
---

<div>
    {% assign categories = site.categories | sort %}
    {% for category in categories %}
        <span class="site-tag">
            <a href="#{{ category | first | slugify }}">
            {{ category[0] | replace:'-', ' ' }} ({{ category | last | size }})
            </a> 
            &nbsp;
        </span>
    {% endfor %}
</div>

<p>&nbsp;</p>
   
<div id="index">
    {% for category in categories %}
        <a name="{{ category[0] }}"></a><h2>{{ category[0] | replace:'-', ' ' }} ({{ category | last | size }}) </h2>
        {% assign sorted_posts = site.posts | sort: 'title' %}
        {% for post in sorted_posts %}
            {% if post.categories contains category[0] %}
                <ul>
                <h4><a href="{{ site.url }}{{site.baseurl}}{{ post.url }}" title="{{ post.title }}">{{ post.title }} </a></h4>
                </ul>
            {% endif %}
        {% endfor %}
        <p> </p>
    {% endfor %}
</div>
{% endraw %}
```
I got the idea from [this](http://digitaldrummerj.me/blogging-on-github-part-5-adding-a-category-page/) blog post. I also modified the code to suit my needs. Make sure to check the original source too!! :)