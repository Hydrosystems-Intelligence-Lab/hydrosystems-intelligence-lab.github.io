---
layout: default
title: Home
description: Abeshu Hydrosystems Intelligence Lab at New Mexico State University.
---

<section class="home-hero" style="--home-hero-image: url('{{ '/assets/img/nm-rio-grande-bosque.jpg' | relative_url }}');">
  <div class="wrapper home-hero-grid">
    <div class="hero-copy">
      <h1>Hydrosystems intelligence for water futures beyond historical experience</h1>
      <p class="hero-lede">At New Mexico State University, the Abeshu Hydrosystems Intelligence Lab (Abeshu HI Lab) develops models, data systems, and decision tools to understand and manage water risk in a changing climate, where past conditions no longer define future water security.</p>
      <div class="button-row">
        <a class="button primary" href="{{ '/research/' | relative_url }}">Explore Research</a>
        <a class="button secondary" href="{{ '/publications/' | relative_url }}">View Publications</a>
        <a class="button secondary" href="{{ '/opportunities/' | relative_url }}">Join the Lab</a>
      </div>
    </div>
  </div>
</section>

<section class="home-intro-section">
  <div class="wrapper home-intro-grid">
    <div class="identity-panel">
      <p class="eyebrow sentence-case">About the Lab</p>
      <h2 class="about-welcome-heading">Welcome to the Abeshu HI Lab</h2>
      <div class="identity-list">
        <div>
          <strong>Who we are.</strong>
          <p>We are a hydrosystems research lab at New Mexico State University studying hydrologic systems, water infrastructure, and coupled human-water processes.</p>
        </div>
        <div>
          <strong>What we do.</strong>
          <p>We characterize water risk and develop modeling, forecasting, and decision-support tools for resilient and equitable water systems.</p>
        </div>
        <div>
          <strong>How we do it.</strong>
          <p>We combine physically grounded modeling, Earth observation, artificial intelligence, optimization, and uncertainty-aware analytics to build tools that are scientifically rigorous and useful in practice.</p>
        </div>
        <div>
          <strong>Research identity.</strong>
          <p>We work on coupled climate-water-energy-infrastructure-society systems, with emphasis on hydrologic prediction, AI and machine learning, Earth observation, infrastructure resilience, and climate adaptation.</p>
        </div>
        <div class="emblem-item">
          <div class="emblem-heading">
            <strong>Our emblem.</strong>
            <figure class="emblem-mark">
              <img src="{{ '/assets/img/awsi-emblem-transparent.png' | relative_url }}" alt="" aria-hidden="true">
            </figure>
          </div>
          <p>The four petals represent climate, water, infrastructure, and society as interconnected systems. Their interlocking form reflects mutual dependence, while the central lens represents data science and hydrosystems intelligence guiding better water decisions.</p>
        </div>
      </div>
      <p class="manual-note">New and prospective lab members can read the <a href="{{ '/manual/' | relative_url }}">Abeshu HI Lab manual</a> for advising expectations, onboarding, workflows, and lab practices.</p>
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
    <span>Prospective doctoral students interested in AI-enabled water systems research are encouraged to connect in Fall 2026 for Spring 2027 admission.</span>
    <a href="{{ '/opportunities/' | relative_url }}">View Opportunity</a>
  </div>
</section>
