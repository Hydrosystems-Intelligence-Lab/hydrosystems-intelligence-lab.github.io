---
layout: page
title: Updates
summary: Announcements, research notes, opportunities, and short posts from the Abeshu Hydrosystems Intelligence Lab.
hero_image: /assets/img/nm-valles-caldera.jpg
hero_image_position: center 50%
content_width: wide
---

<p><a class="text-link" href="{{ '/feed.xml' | relative_url }}">Subscribe to updates via RSS</a></p>

<div class="news-list">
  {% for post in site.posts %}
    <article>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}
        {{ post.excerpt }}
      {% endif %}
    </article>
  {% endfor %}
</div>
