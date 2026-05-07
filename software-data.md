---
layout: page
title: Software & Data
summary: Public datasets, modeling workflows, code practices, and future open-source tools from the HORA Abeshu Lab.
hero_image: /assets/img/nm-white-sands.jpg
hero_image_position: center 52%
content_width: wide
---

<section class="software-data-lead">
  <div>
    <p class="eyebrow">Open Research Outputs</p>
    <h2>Software and data should make the science reusable</h2>
    <p>
      HORA is a new lab, so this page separates existing public datasets and publications from software that will emerge as lab projects mature. The goal is to make code, model workflows, data products, and documentation easy to find and cite.
    </p>
  </div>
  <aside class="deadline-card">
    <span>Lab standard</span>
    <strong>Document early</strong>
    <p>Each public tool or dataset should include a clear purpose, setup instructions, data requirements, citation guidance, and maintainer contact.</p>
  </aside>
</section>

<section class="feature-block">
  <p class="eyebrow">Existing Public Outputs</p>
  <h2>Datasets and software-linked outputs</h2>
  {% assign outputs = site.data.publications.datasets_software.items %}
  {% if outputs.size > 0 %}
    <ul class="publication-list">
      {% for item in outputs %}
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
  {% else %}
    <p class="empty-state">Public datasets and software will be added as they are ready.</p>
  {% endif %}
</section>

<section class="feature-block">
  <p class="eyebrow">Emerging Categories</p>
  <h2>Where HORA software and data products are expected to grow</h2>
  <div class="topic-grid">
    <span>Physics-informed hydrologic modeling</span>
    <span>Earth observation processing</span>
    <span>Lake and reservoir analytics</span>
    <span>Infrastructure operations and decision support</span>
    <span>Water equity and community resilience analysis</span>
    <span>Reproducible figure and workflow templates</span>
  </div>
</section>

<section class="feature-block">
  <p class="eyebrow">Documentation</p>
  <h2>Repository and dataset standards</h2>
  <p>
    The lab manual includes the working standards for repository structure, dependencies, examples, citation guidance, and maintainership.
  </p>
  <div class="button-row light">
    <a class="button secondary" href="{{ '/manual/software/' | relative_url }}">Software standards</a>
    <a class="button secondary" href="{{ '/manual/research-workflows/' | relative_url }}">Research workflows</a>
  </div>
</section>
