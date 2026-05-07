---
layout: page
title: Publications
summary: Selected publications by Dr. Abeshu and collaborators, with HORA Lab outputs to be added as lab projects mature.
hero_image: /assets/img/nm-elephant-butte.jpg
hero_image_position: center 46%
content_width: wide
---

<section class="publication-intro feature-block">
  <p class="eyebrow">Research Outputs</p>
  <h2>Selected publications by Dr. Abeshu and collaborators.</h2>
  <p>
    HORA Lab publications, datasets, and software will be added as lab projects mature. Current outputs are organized by type so peer-reviewed papers and conference abstracts remain clearly separated; public datasets and software-linked outputs are also summarized on the <a href="{{ '/software-data/' | relative_url }}">Software &amp; Data</a> page.
  </p>
</section>

<div class="publication-grid">
  {% for section in site.data.publications %}
    {% assign pub_section = section[1] %}
    <section class="publication-section">
      <h2>{{ pub_section.title }}</h2>
      {% if pub_section.items.size > 0 %}
        {% assign sorted_items = pub_section.items | sort: "year" | reverse %}
        {% assign grouped_items = sorted_items | group_by_exp: "item", "item.year | default: 'Undated'" %}
        {% for year_group in grouped_items %}
          <h3 class="publication-year-heading">{{ year_group.name }}</h3>
          <ul class="publication-list">
            {% for item in year_group.items %}
              <li>
                <strong>{{ item.title }}</strong>
                {% if item.authors %}<span class="publication-authors">{{ item.authors }}</span>{% endif %}
                {% if item.venue or item.year %}
                  <span class="publication-meta">
                    {% if item.venue %}<em>{{ item.venue }}</em>{% endif %}{% if item.year %}{% if item.venue %}, {% endif %}{{ item.year }}{% endif %}
                  </span>
                {% endif %}
                {% if item.doi or item.url %}
                  <span class="publication-links">
                    {% if item.doi %}<a href="https://doi.org/{{ item.doi }}">DOI</a>{% endif %}
                    {% if item.url %}<a href="{{ item.url }}">Link</a>{% endif %}
                  </span>
                {% endif %}
              </li>
            {% endfor %}
          </ul>
        {% endfor %}
      {% else %}
        <p class="empty-state">{{ pub_section.note }}</p>
      {% endif %}
    </section>
  {% endfor %}
</div>
