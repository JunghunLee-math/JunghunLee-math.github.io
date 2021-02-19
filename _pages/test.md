---
layout: single
permalink: /test/
title: "test"
toc: true
---


## Papers

Here I list up my papers, and it is ordered as authors, title, journal, publisher, and etc.


{% for paper in site.data.research.papers %}
  <li>
    {% for author in paper.authors %}
        {{author}},
    {% endfor %}
    <a href="{{ paper.links.arxiv }}">
    {{paper.title}}
    </a>,
    {% if paper.state == "published" %}
        {{paper.journal.name}},
        <a href="{{ paper.links.journal }}">
        {{paper.journal.publisher}}
        </a>,
        {{paper.journal.number}}, 
        {{paper.journal.pages}}, 
        {{paper.journal.year}}   
    {% elsif paper.state == "arxiv" %}
        <a href="{{ paper.links.arxiv }}">
            {{paper.journal.name}}
        </a>, 
    {% endif %}
  </li>
{% endfor %}