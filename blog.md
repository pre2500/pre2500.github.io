---
layout: page
title: Blog
permalink: /blog/
---

{% for post in site.posts %}
  <article>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
    {% if post.tags.size > 0 %}
      <span class="post-tags">
        {% for tag in post.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
      </span>
    {% endif %}
    <p>{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
    <a href="{{ post.url | relative_url }}">Read more &rarr;</a>
  </article>
  <hr>
{% endfor %}

{% if site.posts.size == 0 %}
  <p>No posts yet. Check back soon.</p>
{% endif %}
