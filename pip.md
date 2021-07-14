---
layout: post_index
title: "Post Index Page"
date: 2021-01-11 21:00:00 +0900
permalink: /pip/
---

Welcome to the Post Index Page!

You can browse through the posts from here

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>

    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">({{post.date | date: "%Y-%m-%d"}}) {{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
