---
layout: page
title: Team
summary: Team members, collaborators, and prospective students connected to the Abeshu Hydrosystems Intelligence Lab.
hero_image: /assets/img/nm-rio-grande-gorge.jpg
hero_image_position: center 45%
content_width: wide
---

{% assign pi = site.data.people.pi %}

<section class="person-profile featured-profile{% unless pi.image %} no-photo{% endunless %}">
  {% if pi.image %}
    <picture>
      {% if pi.image_webp %}<source srcset="{{ pi.image_webp | relative_url }}" type="image/webp">{% endif %}
      <img class="profile-photo" src="{{ pi.image | relative_url }}" alt="{{ pi.name }}" width="480" height="480" decoding="async">
    </picture>
  {% endif %}
  <div>
    <p class="eyebrow">Principal Investigator</p>
    <h2>{{ pi.name }}</h2>
    <p><strong>{{ pi.role }}</strong></p>
    <p>
      {{ pi.department }}<br>
      {{ pi.college }}<br>
      {{ pi.institute }}<br>
      {{ pi.institution }}
    </p>
    <p>Email: <a href="mailto:{{ pi.email }}">{{ pi.email }}</a></p>
    {% if pi.links %}
      <div class="profile-links" aria-label="Professional profiles">
        {% for link in pi.links %}
          {% if link.url contains '://' %}
            <a href="{{ link.url }}" target="_blank" rel="noopener noreferrer">{{ link.label }}</a>
          {% else %}
            <a href="{{ link.url | relative_url }}">{{ link.label }}</a>
          {% endif %}
        {% endfor %}
      </div>
    {% endif %}
    <p>{{ pi.bio }}</p>
    {% if pi.focus %}
      <ul class="profile-focus">
        {% for item in pi.focus %}
          <li>{{ item }}</li>
        {% endfor %}
      </ul>
    {% endif %}
    <div class="button-row light">
      <a class="button primary" href="mailto:{{ pi.email }}">Email Dr. Abeshu</a>
      <a class="button secondary" href="{{ '/opportunities/' | relative_url }}">Student Opportunities</a>
    </div>
  </div>
</section>

<section class="feature-block cohort-callout">
  <div>
    <p class="eyebrow">First Cohort</p>
    <h2>Building a research lab around useful water intelligence</h2>
    <p>The Abeshu Hydrosystems Intelligence Lab is recruiting its first researchers as the lab launches at New Mexico State University. Early members will help shape lab culture, workflows, open research practices, and the first generation of lab projects.</p>
  </div>
  <div class="cohort-actions">
    <a class="button primary" href="{{ '/opportunities/' | relative_url }}">View Opening</a>
    <a class="button secondary" href="{{ '/manual/' | relative_url }}">Read Lab Handbook</a>
  </div>
</section>

<section class="page-cluster">
  <div class="section-heading compact-heading">
    <p class="eyebrow">Open Positions</p>
    <h2>Currently recruiting</h2>
    <p>The lab is starting at New Mexico State University and is recruiting its first doctoral researcher. Only positions that are currently open are listed here; future opportunities will be announced on this page and in <a href="{{ '/updates/' | relative_url }}">lab updates</a>.</p>
  </div>
  <div class="role-opportunity-grid">
    {% for role in site.data.people.open_roles %}
      <article class="role-opportunity-card">
        <span class="status-pill available">Open</span>
        <h3>{{ role.role }}</h3>
        <p>{{ role.status }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<div class="group-list collaboration-list">
  {% for group in site.data.people.groups %}
    <section>
      <p class="eyebrow">Partnerships</p>
      <h2>{{ group.name }}</h2>
      <p>{{ group.status }}</p>
    </section>
  {% endfor %}
</div>
