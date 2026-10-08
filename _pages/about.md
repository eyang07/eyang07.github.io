---
layout: about
title: about
permalink: /
subtitle:

profile:
  align: left
  image: prof_pic.jpg
  image_circular: true
  more_info: >
    <a href='https://www.northwestern.edu'>Northwestern University</a><br>
    Computer Engineering &amp; Pure Mathematics<br>
    Math &middot; Formal Methods &middot; AI<br>
    📍 Evanston, IL

selected_papers: false
social: true

announcements:
  enabled: false

latest_posts:
  enabled: false
---

I am a senior at Northwestern University studying Computer Engineering and Mathematics. My research interests are in formal verification, particularly theorem proving and CPS verification. On the side, I am greatly interested in mathematical physics, and I am working on a senior thesis on Edward Witten's spinor geometry proof of the Positive Energy Theorem.

Currently, I work as a research assistant at the IDEAS Lab, where I work on formal verification projects. I also contributed to DeepMind's <a href="https://github.com/google-deepmind/formal-conjectures">Formal Conjectures</a> through the Northwestern Lean Lab.

## Selected work

{% assign featured_research = site.research | where: "featured", true %}
{% assign featured_projects = site.projects | where: "featured", true %}
{% assign featured = featured_research | concat: featured_projects | sort: "importance" %}
{% include entry-list.liquid items=featured empty="Coming soon." %}

## Education

{% include education.liquid %}
