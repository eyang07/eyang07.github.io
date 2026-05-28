---
layout: page
title: talks
permalink: /talks/
description: Slides from class, reading-course, and research presentations.
nav: true
nav_order: 3
---

<div class="talks">
{% assign sorted_talks = site.talks | sort: "date" | reverse %}
<ul>
  {% for talk in sorted_talks %}
    <li>
      <a href="{{ talk.url | relative_url }}"><strong>{{ talk.title }}</strong></a>
      {% if talk.venue %} — <em>{{ talk.venue }}</em>{% endif %}
    </li>
  {% endfor %}
</ul>
</div>
