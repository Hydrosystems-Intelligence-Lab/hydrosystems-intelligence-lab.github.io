---
layout: page
title: Team
summary: Members, collaborators, and prospective students connected to the HORA Abeshu Research Group.
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
      {{ pi.college }}<br>
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

<section class="feature-block cohort-callout">
  <div>
    <p class="eyebrow">First Cohort</p>
    <h2>Building a research group around useful water intelligence</h2>
    <p>HORA is recruiting its first cohort of graduate and undergraduate researchers as the group launches at New Mexico State University. Early members will help shape group culture, workflows, open research practices, and the first generation of HORA projects.</p>
  </div>
  <div class="cohort-actions">
    <a class="button primary" href="{{ '/opportunities/' | relative_url }}">View Openings</a>
    <a class="button secondary" href="{{ '/manual/' | relative_url }}">Read Group Manual</a>
  </div>
</section>

<section class="page-cluster">
  <div class="section-heading compact-heading">
    <p class="eyebrow">Future Team Members</p>
    <h2>Students and postdoctoral researchers</h2>
    <p>Roles will open as funded projects and mentoring capacity become available.</p>
  </div>
  <div class="role-opportunity-grid">
    {% for role in site.data.people.open_roles %}
      <article class="role-opportunity-card">
        <span class="status-pill">Future role</span>
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
