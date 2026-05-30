---
layout: page
title: Topological Entropy
term: Spring 2026
venue: Northwestern Math Department
permalink: /presentations/topological-entropy/
---

{% if page.venue %}*Presented at {{ page.venue }}{% if page.term %}, {{ page.term }}{% endif %}.*{% elsif page.term %}*{{ page.term }}.*{% endif %}

<a href="{{ page.slides | relative_url | uri_escape }}" class="btn btn-sm z-depth-0" target="_blank">
  <i class="fas fa-file-pdf"></i> Download slides (PDF)
</a>

<iframe src="{{ page.slides | relative_url | uri_escape }}" width="100%" height="700px" style="border: 1px solid #ccc; margin-top: 1em;"></iframe>
