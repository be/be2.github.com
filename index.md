---
layout: page
title: Latest
tagline:
---
{% include JB/setup %}



<ul class="posts">
  {% for post in site.posts limit:10 %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
[*← earlier*](/archive.html)




BTC:

![donate](https://dl.dropboxusercontent.com/u/5666518/canvas.png)

    1JuzbgBxewwcodndvn6eQqU99fNvkL5nDP

