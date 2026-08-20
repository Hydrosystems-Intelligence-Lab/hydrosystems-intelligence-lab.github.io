---
layout: page
title: Software & Data
summary: Open-source models, code, and datasets from the Abeshu Hydrosystems Intelligence Lab, and the standards they are published under.
hero_image: /assets/img/nm-white-sands.jpg
hero_image_position: center 52%
content_width: wide
---

{% assign model_count = site.data.software.models.items | size %}
{% assign dataset_count = site.data.software.datasets.items | size %}
{% assign release_count = model_count | plus: dataset_count %}

<section class="software-data-lead">
  <div>
    <p class="eyebrow">Open Research Outputs</p>
    <h2>Open models, code, and data</h2>
    <p>
      Models and datasets developed by Dr. Abeshu and collaborators are released publicly with a permanent DOI, so that results can be reproduced and the underlying data reused. The releases below span global hydrological modeling, lake and reservoir representation, water management, and hydropower availability.
    </p>
    <p>
      Papers that use these products are listed on the <a href="{{ '/publications/' | relative_url }}">publications</a> page. New releases from the lab's own projects will be added here as those projects mature.
    </p>
  </div>
  <aside class="deadline-card">
    <span>Lab standard</span>
    <strong>Document early</strong>
    <p>Each public tool or dataset includes a clear purpose, setup instructions, data requirements, citation guidance, and maintainer contact.</p>
  </aside>
</section>

<section class="publication-intro feature-block page-priority">
  <div>
    <p class="eyebrow">Citation</p>
    <h2>How to cite these releases</h2>
    <p>
      Each item below carries its own DOI. Please cite the release directly rather than linking to a repository URL, and cite the accompanying paper as well where one exists.
    </p>
  </div>
  <div class="summary-stat-grid compact-stats" aria-label="Software and data summary">
    <article class="stat-card">
      <span>{{ release_count }}</span>
      <strong>Public releases</strong>
    </article>
    <article class="stat-card">
      <span>{{ model_count }}</span>
      <strong>Models and code</strong>
    </article>
    <article class="stat-card">
      <span>{{ dataset_count }}</span>
      <strong>Datasets</strong>
    </article>
  </div>
</section>

<div class="publication-grid">
  {% for section in site.data.software %}
    {% assign sw_section = section[1] %}
    <section class="publication-section">
      <div class="publication-section-header">
        <div>
          <p class="eyebrow">Output Type</p>
          <h2>{{ sw_section.title }}</h2>
        </div>
        {% if sw_section.items.size > 0 %}
          <span class="status-pill">{{ sw_section.items.size }} listed</span>
        {% else %}
          <span class="status-pill muted">In progress</span>
        {% endif %}
      </div>
      {% if sw_section.items.size > 0 %}
        {% assign sorted_items = sw_section.items | sort: "year" | reverse %}
        {% assign grouped_items = sorted_items | group_by_exp: "item", "item.year | default: 'Undated'" %}
        {% for year_group in grouped_items %}
          <h3 class="publication-year-heading">{{ year_group.name }}</h3>
          <ul class="publication-list">
            {% for item in year_group.items %}
              <li>
                <strong>{{ item.title }}</strong>
                {% if item.summary %}<span class="publication-summary">{{ item.summary }}</span>{% endif %}
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
        <p class="empty-state">{{ sw_section.note }}</p>
      {% endif %}
    </section>
  {% endfor %}
</div>

<section class="application-panel">
  <div>
    <p class="eyebrow">Documentation</p>
    <h2>Repository and dataset standards</h2>
    <p>The research lab handbook includes working standards for repository structure, dependencies, examples, citation guidance, and maintainership.</p>
  </div>
  <div>
    <p class="eyebrow">Reference</p>
    <h2>Lab workflows</h2>
    <div class="button-row light">
      <a class="button secondary" href="{{ '/manual/software/' | relative_url }}">Software standards</a>
      <a class="button secondary" href="{{ '/manual/research-workflows/' | relative_url }}">Research workflows</a>
    </div>
  </div>
</section>
