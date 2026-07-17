---
layout: page
title: Research
summary: Research in the Abeshu Hydrosystems Intelligence Lab centers on connected directions that use physics-informed AI, multi-sensor Earth observation, and decision analytics to improve water resilience from local infrastructure to global Earth-system models.
hero_image: /assets/img/nm-organ-mountains.jpg
hero_image_position: center center
content_width: wide
---

<div class="portfolio-intro">
  <p class="eyebrow">Adaptive Portfolio</p>
  <h2>Research built for interpretation, transfer, and use</h2>
  <p class="portfolio-lede">The lab develops learning-based methods that respect physical structure, combine multiple sources of evidence, and produce decision-relevant outputs. The work is designed for settings where water managers and communities need robust information despite uncertain climate, aging infrastructure, and uneven water security.</p>
  <div class="method-tags" aria-label="Research methods">
    <span>Physics-informed AI</span>
    <span>Remote sensing</span>
    <span>Hydrologic modeling</span>
    <span>Optimization</span>
    <span>Equity analytics</span>
  </div>
  <ol class="thrust-index" aria-label="Research thrusts">
    {% for area in site.data.research %}
      <li>
        <a href="#{{ area.icon }}">
          <span class="thrust-num">{% if forloop.index < 10 %}0{{ forloop.index }}{% else %}{{ forloop.index }}{% endif %}</span>
          {{ area.title }}
        </a>
      </li>
    {% endfor %}
  </ol>
</div>

<div class="research-stack">
  {% for area in site.data.research %}
    <section class="feature-block research-detail" id="{{ area.icon }}">
      {% if area.image %}
        <button
          class="research-detail-media js-image-zoom"
          type="button"
          data-full-src="{{ area.image | relative_url }}"
          data-alt="{{ area.image_alt | default: area.title }}"
          aria-label="View larger image: {{ area.title }}"
        >
          <img class="research-detail-image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt | default: area.title }}" loading="lazy">
        </button>
      {% endif %}
      <div class="research-detail-copy">
        <p class="eyebrow">Thrust {{ forloop.index }}</p>
        <h2>{{ area.title }}</h2>
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

<div class="portfolio-intro">
  <p class="eyebrow">Research Foundations</p>
  <h2>Prior work the lab builds on</h2>
  <p class="portfolio-lede">The lab's research directions grow out of published work on water management in large-scale models, catchment water balance and vegetation response, and unprecedented hydrologic extremes.</p>
</div>

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
</div>
