---
layout: page
title: AI-Assisted Theorem Proving in Lean
date: 2026-02-01
venue:
slides: /assets/pdf/presentations/AI-Assisted Theorem Proving.pdf
permalink: /presentations/ai-assisted-theorem-proving-in-lean/
---

{% if page.venue %}*Presented at {{ page.venue }} on {{ page.date | date: "%B %-d, %Y" }}.*{% else %}*{{ page.date | date: "%B %-d, %Y" }}.*{% endif %}

<a href="{{ page.slides | relative_url | uri_escape }}" class="btn btn-sm z-depth-0" target="_blank">
  <i class="fas fa-file-pdf"></i> Download slides (PDF)
</a>

<iframe src="{{ page.slides | relative_url | uri_escape }}" width="100%" height="700px" style="border: 1px solid #ccc; margin-top: 1em;"></iframe>
