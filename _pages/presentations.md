---
layout: page
title: presentations
permalink: /presentations/
description: Slides from class, reading-course, and research presentations.
nav: true
nav_order: 3
---

<div class="presentations">
{% assign sorted_presentations = site.presentations | sort: "term" | reverse %}

<h2>At Northwestern</h2>

<ul>
  {% for presentation in sorted_presentations %}
    <li>
      <a href="{{ presentation.url | relative_url }}"><strong>{{ presentation.title }}</strong></a>
      {% if presentation.venue %} — <em>{{ presentation.venue }}</em>{% endif %}
      {% if presentation.term %} <span style="color: gray;">({{ presentation.term }})</span>{% endif %}
      {% if presentation.slides %} · <a href="{{ presentation.slides | relative_url | uri_escape }}">[pdf]</a>{% endif %}
    </li>
  {% endfor %}
</ul>
</div>
