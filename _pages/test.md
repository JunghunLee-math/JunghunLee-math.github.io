---
layout: single
permalink: /test/
title: "test"
toc: true
---

{% for paper in site.data.research.papers %}
  <li>
  {{paper}}
  </li>
{% endfor %}
