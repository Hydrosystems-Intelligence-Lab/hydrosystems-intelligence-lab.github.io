---
layout: page
title: Publications
summary: Selected publications by Dr. Abeshu and collaborators that ground the research direction of the Abeshu Hydrosystems Intelligence Lab.
hero_image: /assets/img/nm-elephant-butte.jpg
hero_image_position: center 46%
content_width: wide
---

{% assign peer_count = site.data.publications.journal_articles.items | size %}
{% assign conference_count = site.data.publications.conference_papers.items | size %}
{% assign preprint_count = site.data.publications.preprints.items | size %}
{% assign total_count = peer_count | plus: conference_count | plus: preprint_count %}

<section class="publication-intro feature-block page-priority">
  <div>
    <p class="eyebrow">Research Outputs</p>
    <h2>Selected publications shaping the lab's research direction</h2>
    <p>
      These publications reflect the scholarly foundation around which the Abeshu Hydrosystems Intelligence Lab is being launched. Lab-authored outputs will be added here as the lab's first projects mature.
    </p>
    {% assign scholar_link = site.data.people.pi.links | where: "label", "Google Scholar" | first %}
    {% if scholar_link %}
      <a class="text-link" href="{{ scholar_link.url }}">Full publication list on Google Scholar</a>
    {% endif %}
  </div>
  <div class="summary-stat-grid compact-stats" aria-label="Publication summary">
    <article class="stat-card">
      <span>{{ total_count }}</span>
      <strong>Selected outputs</strong>
    </article>
    <article class="stat-card">
      <span>{{ peer_count }}</span>
      <strong>Peer-reviewed papers</strong>
    </article>
    <article class="stat-card">
      <span>{{ preprint_count }}</span>
      <strong>Preprints</strong>
    </article>
    <article class="stat-card">
      <span>{{ conference_count }}</span>
      <strong>Conference outputs</strong>
    </article>
  </div>
</section>

<div class="publication-grid">
  {% for section in site.data.publications %}
    {% assign pub_section = section[1] %}
    <section class="publication-section">
      <div class="publication-section-header">
        <div>
          <p class="eyebrow">Output Type</p>
          <h2>{{ pub_section.title }}</h2>
        </div>
        {% if pub_section.items.size > 0 %}
          <span class="status-pill">{{ pub_section.items.size }} listed</span>
        {% else %}
          <span class="status-pill muted">In progress</span>
        {% endif %}
      </div>
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
