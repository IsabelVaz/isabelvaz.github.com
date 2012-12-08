---
layout: page
title: Isabel Vaz Labores
tagline: Labores caseiros albicastrenses
---
{% include JB/setup %}

## Ultimos labores

<div class="posts">
  {% for post in site.posts %}
    <div class="post">
      <a href="{{ BASE_PATH }}{{ post.url }}" ><img width="300" height="200" src="{{ post.img }}" alt="{{ post.title }}" /> </a>
    </div>
  {% endfor %}
</div>

<!--
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
    <br />
    {{ post.content }} 
    <br />
    </li>
  {% endfor %}
</ul>
-->
