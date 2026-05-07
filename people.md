---
layout: page
title: Team
summary: Members, collaborators, and prospective students connected to the HORA Abeshu Lab.
hero_image: /assets/img/nm-rio-grande-gorge.jpg
hero_image_position: center 45%
content_width: wide
---

{% assign pi = site.data.people.pi %}

<section class="person-profile featured-profile{% unless pi.image %} no-photo{% endunless %}">
  {% if pi.image %}
    <img class="profile-photo" src="{{ pi.image | relative_url }}" alt="{{ pi.name }}">
  {% endif %}
  <div>
    <p class="eyebrow">Principal Investigator</p>
    <h2>{{ pi.name }}</h2>
    <p><strong>{{ pi.role }}</strong></p>
    <p>
      {{ pi.department }}<br>
      {{ pi.institute }}<br>
      {{ pi.institution }}
    </p>
    <p>Email: <a href="mailto:{{ pi.email }}">{{ pi.email }}</a></p>
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

<section class="feature-block">
  <p>HORA is building its first cohort of graduate and undergraduate researchers as the lab launches at New Mexico State University.</p>
</section>

<section class="feature-block">
  <p class="eyebrow">Future Team Members</p>
  <h2>Students and Postdoctoral Researchers</h2>
  <div class="team-card-grid">
    {% for role in site.data.people.open_roles %}
      <article class="placeholder-profile">
        <img class="placeholder-avatar" src="{{ role.image | relative_url }}" alt="" aria-hidden="true" loading="lazy">
        <div>
          <h3>{{ role.name }}</h3>
          <p><strong>{{ role.role }}</strong></p>
          <p>{{ role.status }}</p>
        </div>
      </article>
    {% endfor %}
  </div>
</section>

<div class="group-list">
  {% for group in site.data.people.groups %}
    <section>
      <h2>{{ group.name }}</h2>
      <p>{{ group.status }}</p>
    </section>
  {% endfor %}
</div>
