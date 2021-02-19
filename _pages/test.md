---
layout: single
permalink: /test/
title: "test"
toc: true
---


## Papers

<ol>
{% for paper in site.data.research.papers %}
  <li>
    {% for author in paper.authors %}
        {{author}},
    {% endfor %}
    {% if paper.links.arXiv.blank? %}
        {{paper.title}},
    {% else %}
        <a href="{{ paper.links.arXiv }}">
            {{paper.title}}
        </a>,
    {% endif %}    
    {% if paper.state == "published" %}
        <a href="{{ paper.links.journal }}">
        {{paper.journal.name}}
        </a>,
        {{paper.journal.publisher}},
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
</ol>

## Talks

<ol>
{% for talk in site.data.research.talks %}
  <li>
    {% for author in talk.authors %}
        {{author}},
    {% endfor %}
    {{talk.title}},
    <a href="{{ talk.talk.link }}">
        {{talk.talk.name}},
    </a>
    {{talk.talk.place.city}} ({{talk.talk.place.country}}),
    {{talk.talk.date.month}} {{talk.talk.date.year}}
  </li>
{% endfor %}
</ol>