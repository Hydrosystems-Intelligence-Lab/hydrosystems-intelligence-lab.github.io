---
layout: page
title: Updates
summary: Announcements, research notes, opportunities, and short updates from the HORA Abeshu Research Group.
hero_image: /assets/img/nm-valles-caldera.jpg
hero_image_position: center 50%
---

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
