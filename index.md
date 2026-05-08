---
layout: default
title: Home
description: HORA Abeshu Research Group at New Mexico State University.
---

<section class="home-hero" style="--home-hero-image: url('{{ '/assets/img/nm-rio-grande-bosque.jpg' | relative_url }}');">
  <div class="wrapper home-hero-grid">
    <div class="hero-copy">
      <h1>Hydrosystems intelligence for water futures beyond the past</h1>
      <p class="hero-lede">At New Mexico State University, the Hydrosystems Operational Intelligence for Resilience and Adaptation (HORA) Research Group develops physics-informed AI, Earth observation, and decision-support tools for resilient and equitable water systems.</p>
      <div class="button-row">
        <a class="button primary" href="{{ '/research/' | relative_url }}">Explore Research</a>
        <a class="button secondary" href="{{ '/publications/' | relative_url }}">View Publications</a>
        <a class="button secondary" href="{{ '/opportunities/' | relative_url }}">Join the Group</a>
      </div>
    </div>
  </div>
</section>

<section class="home-intro-section">
  <div class="wrapper home-intro-grid">
    <div class="identity-panel">
      <p class="eyebrow sentence-case">About HORA</p>
      <h2 class="about-welcome-heading">Welcome to the HORA Abeshu Research Group</h2>
      <div class="identity-list">
        <div>
          <strong>Who we are.</strong>
          <p>We are a research group at New Mexico State University studying hydrologic systems, water infrastructure, and coupled human-water processes.</p>
        </div>
        <div>
          <strong>What we do.</strong>
          <p>We characterize water risk and develop modeling, forecasting, and decision-support tools for resilient and equitable water systems.</p>
        </div>
        <div>
          <strong>How we do it.</strong>
          <p>We combine physically grounded modeling, Earth observation, artificial intelligence, optimization, and uncertainty-aware analytics — building tools that are both scientifically rigorous and useful in practice.</p>
        </div>
        <div>
          <strong>Our story.</strong>
          <p>HORA Abeshu Research Group launches at NMSU in 2026. Our group name draws inspiration from the <a href="https://en.wikipedia.org/wiki/Oromo_people">Oromo</a> word hora, symbolizing life-giving water, community, and resilience. We work where data is sparse, decisions are urgent, and communities depend on getting it right.</p>
        </div>
      </div>
      <p class="manual-note">New and prospective group members can read the <a href="{{ '/manual/' | relative_url }}">HORA Research Group Manual</a> for advising expectations, onboarding, workflows, and group practices.</p>
    </div>
    <aside class="home-news-panel" aria-label="Recent updates">
      <div class="panel-heading-row">
        <p class="eyebrow">Recent Updates</p>
        <a class="small-link" href="{{ '/updates/' | relative_url }}">View all</a>
      </div>
      <div class="news-list compact">
        {% assign news_count = 0 %}
        {% for post in site.posts %}
          {% if news_count < 3 %}
            <article>
              <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
              <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
            </article>
            {% assign news_count = news_count | plus: 1 %}
          {% endif %}
        {% endfor %}
      </div>
    </aside>
  </div>
</section>

<section class="notice-band">
  <div class="wrapper notice">
    <strong>Funded PhD opportunity:</strong>
    <span>Prospective doctoral students interested in AI-enabled water systems research are encouraged to connect for Spring 2027 admission.</span>
    <a href="{{ '/opportunities/' | relative_url }}">View Opportunity</a>
  </div>
</section>
