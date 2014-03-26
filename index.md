---
layout: default
title: A little knowledge
date: 2014-03-26 09:00:00 UTC
---

A little knowledge is a dangerous thing.  
And this file is index.html in at the root.  
And a change here is reflected in the `_site` version if I run jekyll build.  

Now I have added the YAML front matter.

1. One
2. Two
3. Three
4. Four


Posts
-----

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

