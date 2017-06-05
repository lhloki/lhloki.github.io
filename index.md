---
layout: page
title: Hello World!
tagline: 活在自己最年轻的一天！
---
{% include JB/setup %}


## All Posts


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


