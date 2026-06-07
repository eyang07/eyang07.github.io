---
layout: page
title: notes
permalink: /notes/
description: Course notes.
nav: true
nav_order: 5
---

<div class="notes">
{% assign sorted_notes = site.notes | sort: "course_code" %}

<h2>Class Notes</h2>

<ul>
  {% for note in sorted_notes %}
    <li>
      <a href="{{ note.url | relative_url }}"><strong>{{ note.course_code }}</strong>: {{ note.title }}</a>
    </li>
  {% endfor %}
</ul>
</div>
