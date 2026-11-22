---
layout: page
permalink: /ai-notes/
title: Notes on AI Papers
nav_title: AI notes
nav: true
nav_order: 7
description: I share the ideas, derivations, and questions I work through while reading AI papers.
---

{% assign notes = site.ai_notes | sort: "date" | reverse %}
{% if notes.size > 0 %}

<ul class="post-list">
  {% for note in notes %}
    <li>
      <h2 class="h4"><a href="{{ note.url | relative_url }}">{{ note.title | escape }}</a></h2>
      {% if note.description and note.description != empty %}
        <p>{{ note.description | escape }}</p>
      {% endif %}
      <p class="post-meta">
        <time datetime="{{ note.date | date: '%Y-%m-%d' }}">{{ note.date | date: '%b %d, %Y' }}</time>
        {% if note.paper_url and note.paper_url != empty %}
          &middot; <a href="{{ note.paper_url | escape }}">Original paper</a>
        {% endif %}
      </p>
    </li>
  {% endfor %}
</ul>

{% else %}

The first note will appear here.

{% endif %}
