--- 
layout: default 
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
            {%if post.categories contains category[0]%} 
                <ul> 
                <h4><a href="{{site.baseurl}}{{ post.url }}" title="{{ post.title }}">{{ post.title }} </a></h4> 
                </ul> 
            {%endif%} 
        {% endfor %} 
        <p> </p> 
    {% endfor %} 
</div>