---
layout: page
title: notes
permalink: /notes/
description: Course notes.
nav: true
nav_order: 5
---

{% assign sorted_notes = site.notes | sort: "course_code" %}
{% include entry-list.liquid items=sorted_notes group_by="department" empty="Notes coming soon." %}
