---
layout: page
title: Archive
---

<!-- <div class="related">
  <h2>Pages</h2>
  <ul class="related-posts">
    {% for page in site.pages%}
      <li>
        <h3>
          <a href="{{ site.url }}{{ page.url }}">
            {{ page.title }}
          </a>
        </h3>
      </li>
    {% endfor %}
  </ul>
</div> -->

<div class="related">
  <h2>Posts</h2>
  <ul class="related-posts">
    {% for post in site.posts%}
      <li>
        <h3>
          <a href="{{ site.url }}{{ post.url }}">
            {{ post.title }}
            <small>{{ post.date | date_to_string }}</small>
          </a>
        </h3>
      </li>
    {% endfor %}
  </ul>
</div>