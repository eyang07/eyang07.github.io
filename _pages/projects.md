---
layout: page
title: projects
permalink: /projects/
nav: true
nav_order: 3
---

{% assign sorted_projects = site.projects | sort: "importance" %}
{% include entry-list.liquid items=sorted_projects empty="Coming soon." %}
