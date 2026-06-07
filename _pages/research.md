---
layout: page
title: research
permalink: /research/
nav: true
nav_order: 2
---

{% assign sorted_research = site.research | sort: "importance" %}
{% include entry-list.liquid items=sorted_research empty="Coming soon." %}
