---
layout: post
title: Post Index Page

permalink: /pip/
---

List of the posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>