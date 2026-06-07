---
layout: page
title: presentations
permalink: /presentations/
nav: true
nav_order: 4
---

{% assign sorted_presentations = site.presentations | sort: "year" | reverse %}
{% include entry-list.liquid items=sorted_presentations group_by="year" empty="Coming soon." %}
