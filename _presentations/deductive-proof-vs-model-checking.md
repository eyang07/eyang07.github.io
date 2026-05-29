---
layout: page
title: Deductive Proof vs. Model Checking
date: Spring 2026
venue: Northwestern Undergraduate Research Expo
slides: /assets/pdf/presentations/Deductive Proof vs. Model Checking.pdf
permalink: /presentations/deductive-proof-vs-model-checking/
---

{% if page.venue %}*Presented at {{ page.venue }} on {{ page.date | date: "%B %-d, %Y" }}.*{% else %}*{{ page.date | date: "%B %-d, %Y" }}.*{% endif %}

<a href="{{ page.slides | relative_url | uri_escape }}" class="btn btn-sm z-depth-0" target="_blank">
  <i class="fas fa-file-pdf"></i> Download slides (PDF)
</a>

<iframe src="{{ page.slides | relative_url | uri_escape }}" width="100%" height="700px" style="border: 1px solid #ccc; margin-top: 1em;"></iframe>
