---
layout: page
title: Research
summary: Research in the Abeshu Hydrosystems Intelligence Lab centers on connected directions that use physics-informed AI, multi-sensor Earth observation, and decision analytics to improve water resilience from local infrastructure to global Earth-system models.
hero_image: /assets/img/nm-organ-mountains.jpg
hero_image_position: center center
content_width: wide
---

<div class="portfolio-intro">
  <p class="eyebrow">Research Pillars</p>
  <h2>Three pillars, built for interpretation, transfer, and use</h2>
  <p class="portfolio-lede">The lab develops learning-based methods that respect physical structure, combine multiple sources of evidence, and produce decision-relevant outputs. The work is organized around three pillars, from understanding how water moves to supporting the people and systems that manage it.</p>
  <ol class="thrust-index" aria-label="Research pillars">
    {% for pillar in site.data.pillars %}
      <li>
        <a href="#{{ pillar.id }}">
          <span class="thrust-num">{% if forloop.index < 10 %}0{{ forloop.index }}{% else %}{{ forloop.index }}{% endif %}</span>
          {{ pillar.title }}
        </a>
      </li>
    {% endfor %}
  </ol>
</div>

{% for pillar in site.data.pillars %}
  {% assign pillar_areas = site.data.research | where: "pillar", pillar.id %}
  <section class="research-pillar" id="{{ pillar.id }}">
    <div class="section-heading compact-heading">
      <p class="eyebrow">Pillar {{ forloop.index }}</p>
      <h2>{{ pillar.title }}</h2>
      <p>{{ pillar.summary }}</p>
      {% if pillar.scope %}
        <div class="method-tags" aria-label="Topics in {{ pillar.title }}">
          {% for item in pillar.scope %}<span>{{ item }}</span>{% endfor %}
        </div>
      {% endif %}
    </div>

    <div class="research-stack">
      {% for area in pillar_areas %}
        <section class="feature-block research-detail{% unless area.feature_image %} no-media{% endunless %}" id="{{ area.icon }}">
          {% if area.image and area.feature_image %}
            <button
              class="research-detail-media js-image-zoom"
              type="button"
              data-full-src="{{ area.image | relative_url }}"
              data-alt="{{ area.image_alt | default: area.title }}"
              aria-label="View larger image: {{ area.title }}"
            >
              <picture>
                {% if area.image_webp %}<source srcset="{{ area.image_webp | relative_url }}" type="image/webp">{% endif %}
                <img class="research-detail-image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt | default: area.title }}" width="760" height="760" loading="lazy" decoding="async">
              </picture>
            </button>
          {% endif %}
          <div class="research-detail-copy">
            <h3>{{ area.title }}</h3>
            <p>{{ area.summary }}</p>
            {% if area.focus %}
              <ul class="research-focus">
                {% for item in area.focus %}
                  <li>{{ item }}</li>
                {% endfor %}
              </ul>
            {% endif %}
            {% if area.outcomes %}
              <p class="research-outcome"><strong>Applications:</strong> {{ area.outcomes }}</p>
            {% endif %}
          </div>
        </section>
      {% endfor %}
    </div>
  </section>
{% endfor %}

<div class="portfolio-intro">
  <p class="eyebrow">Cross-Cutting Methods</p>
  <h2>Methods used across all three pillars</h2>
  <p class="portfolio-lede">The same methodological core supports every pillar, which is what lets results transfer between them.</p>
  <div class="method-tags" aria-label="Cross-cutting methods">
    <span>Scientific AI and machine learning</span>
    <span>Earth observation and remote sensing</span>
    <span>Environmental informatics</span>
    <span>Hydrologic and Earth-system modeling</span>
    <span>Uncertainty quantification</span>
  </div>
  <p class="image-note">Illustrations on this page are AI-generated diagrams used to introduce each pillar. They are illustrative only and do not present research results or data.</p>
</div>
<!-- 
<div class="portfolio-intro">
  <p class="eyebrow">Research Foundations</p>
  <h2>Prior work the lab builds on</h2>
  <p class="portfolio-lede">The lab's research directions grow out of published work on water management in large-scale models, catchment water balance and vegetation response, and unprecedented hydrologic extremes.</p>
</div> -->
<!-- 
<div class="highlight-grid">
  {% for item in site.data.highlights %}
    <article class="highlight-card">
      {% if item.label %}<span>{{ item.label }}</span>{% endif %}
      <h3>{{ item.title }}</h3>
      <p>{{ item.summary }}</p>
      {% if item.evidence %}
        <p class="highlight-evidence">{{ item.evidence }}</p>
      {% endif %}
      {% if item.links %}
        <div class="highlight-links">
          {% for link in item.links %}
            <a href="{{ link.url }}">{{ link.text }}</a>
          {% endfor %}
        </div>
      {% endif %}
    </article>
  {% endfor %}
</div> -->
