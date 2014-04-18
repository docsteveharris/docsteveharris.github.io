---
layout: default
title: A little knowledge
date: 2014-03-26 09:00:00 UTC
---

A little knowledge is a dangerous thing.  

Posts
-----

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

