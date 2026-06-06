---
layout: page
title: projects
permalink: /projects/
description: A collection of projects.
nav: true
nav_order: 3
---

<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}
{% if sorted_projects.size > 0 %}
<ul>
  {% for project in sorted_projects %}
    <li>
      <a href="{{ project.url | relative_url }}"><strong>{{ project.title }}</strong></a>
      {% if project.context %} <span style="color: gray;">({{ project.context }})</span>{% endif %}
    </li>
  {% endfor %}
</ul>
{% else %}
  <p><em>Coming soon.</em></p>
{% endif %}
</div>
