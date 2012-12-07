---
layout: page
title: Isabel Vaz Labores
tagline: Labores caseiros albicastrenses
---
{% include JB/setup %}

## Ultimos labores

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
    <br />
    {{ post.content }} 
    <br />
    </li>
  {% endfor %}
</ul>
