---
layout: single
permalink: /test/
title: "test"
toc: true
---


## Papers

### Published

<ol>
{% for paper in site.data.research.papers %}
  <li>
    {% for author in paper.authors %}
        {{author}},
    {% endfor %}
    {% if paper.links.arxiv.blank? == true %}
        <a href="{{ paper.links.arxiv }}">
        {{paper.title}}
        </a>,
    {% else %}
        {{paper.title}},
    {% endif %}    
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
</ol>

## Talks

{% for talk in site.data.research.talks %}
  <li>
    {% for author in talk.authors %}
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