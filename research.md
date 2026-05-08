---
layout: page
title: Research
summary: Research in HORA centers on five connected directions that use physics-informed AI, multi-sensor Earth observation, and decision analytics to improve water resilience from local infrastructure to global Earth-system models.
hero_image: /assets/img/nm-organ-mountains.jpg
hero_image_position: center center
content_width: wide
---

<section class="research-overview" aria-label="HORA research overview">
  <figure class="visual-card research-visual">
    <img src="{{ '/assets/img/hora-research-concept.png' | relative_url }}" alt="Illustration of connected hydrologic, climate, community, infrastructure, and urban water systems." loading="lazy">
    <figcaption>
      <!-- HORA studies connected hydrosystems where climate, infrastructure, communities, and operational decisions interact. -->
    </figcaption>
  </figure>
  <div class="research-overview-copy">
    <p class="eyebrow">Integrated Portfolio</p>
    <h2>Research built for interpretation, transfer, and use</h2>
    <p>
      The group develops learning-based methods that respect physical structure, combine multiple sources of evidence, and produce decision-relevant outputs. The work is designed for settings where water managers and communities need robust information despite uncertain climate, aging infrastructure, and uneven water security.
    </p>
    <div class="method-tags" aria-label="Research methods">
      <span>Physics-informed AI</span>
      <span>Remote sensing</span>
      <span>Hydrologic modeling</span>
      <span>Optimization</span>
      <span>Equity analytics</span>
    </div>
  </div>
</section>

<div class="research-stack">
  {% for area in site.data.research %}
    <section class="feature-block research-detail" id="{{ area.icon }}">
      {% if area.image %}
        <img class="research-detail-image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt | default: area.title }}" loading="lazy">
      {% endif %}
      <div class="research-detail-copy">
        <p class="eyebrow">Direction {{ forloop.index }}</p>
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
