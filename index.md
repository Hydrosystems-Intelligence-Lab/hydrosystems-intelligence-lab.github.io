---
layout: default
title: Home
description: Abeshu Hydrosystems Intelligence Group at New Mexico State University.
---

<section class="home-hero" style="--home-hero-image: url('{{ '/assets/img/nm-rio-grande-bosque.jpg' | relative_url }}');">
  <div class="wrapper home-hero-grid">
    <div class="hero-copy">
      <h1>Navigating water futures beyond the bounds of history</h1>
      <p class="hero-lede">At New Mexico State University, the Abeshu Hydrosystems Intelligence Group develops models, data systems, and decision tools to understand and manage water risk in a changing climate, where past conditions no longer define future water security.</p>
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
      <p class="eyebrow sentence-case">About the Group</p>
      <h2 class="about-welcome-heading">Welcome to our website!</h2>
      <div class="identity-list">
        <div>
          <strong>Who we are.</strong>
          <p>We are a hydrosystems research group in the Department of Civil and Environmental Engineering at New Mexico State University.</p>
        </div>
        <div>
          <strong>What we do.</strong>
          <p>We study water risk under climate stress and develop forecasts, models, and decision-support tools for resilient and equitable water management.</p>
        </div>
        <div>
          <strong>How we do it.</strong>
          <p>Our approach integrates process-based science, Earth observation, AI, optimization, and uncertainty analysis.</p>
        </div>
        <div>
          <strong>Research identity.</strong>
          <p>The group connects prediction, adaptation, infrastructure resilience, and equity across watersheds, regions, and Earth-system scales.</p>
        </div>
        <div class="emblem-item">
          <div class="emblem-heading">
            <strong>Our emblem.</strong>
            <figure class="emblem-mark">
              <img src="{{ '/assets/img/AWSI.png' | relative_url }}" alt="" aria-hidden="true">
            </figure>
          </div>
          <p>The blue emblem reads as two interlocking loops, four interacting petals, and a continuous adaptive cycle. The petals represent climate, water, infrastructure, and human dynamics as distinct but inseparable parts of a complex adaptive hydrosystem. Their circular motion reflects feedbacks among these systems, while the central mark represents hydrosystems intelligence: data, modeling, monitoring, and decision support for better water decisions.</p>
        </div>
      </div>
      <p class="manual-note">New and prospective group members can read the <a href="{{ '/manual/' | relative_url }}">Abeshu Hydrosystems Intelligence Group handbook</a> for advising expectations, onboarding, workflows, and group practices.</p>
    </div>
    <aside class="home-news-panel" aria-label="Recent updates">
      <div class="panel-heading-row">
        <p class="eyebrow">Recent Updates</p>
        <a class="small-link" href="{{ '/updates/' | relative_url }}">View all</a>
      </div>
      <div class="news-list compact">
        {% for post in site.posts limit: 3 %}
          <article>
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
            <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          </article>
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
