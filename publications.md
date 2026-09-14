---
layout: page
title: Publications
permalink: /publications/
---

<!-- Entries live in _data/publications.yml -->
<div class="publications">
{% assign by_year = site.data.publications | group_by: "year" %}
{% for group in by_year %}
  <h2 class="year">{{ group.name }}</h2>
  <ol class="bibliography">
  {% for pub in group.items %}
    <li class="pub">
      <div class="pub-badges">
        <abbr class="badge">{{ pub.abbr }}</abbr>
        {% if pub.award %}<abbr class="badge award">{{ pub.award }}</abbr>{% endif %}
      </div>
      <div class="pub-body">
        <div class="pub-title">{{ pub.title }}</div>
        <div class="pub-authors">
          {% for author in pub.authors %}
            {% if forloop.last and forloop.length > 1 %}and {% endif %}
            {% if site.me contains author %}<strong><u>{{ author }}</u></strong>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        </div>
        <div class="pub-venue"><em>In {{ pub.venue }}</em> {{ pub.year }}</div>
        {% if pub.links %}
        <div class="pub-links">
          {% for link in pub.links %}<a class="btn" href="{{ link[1] }}" target="_blank" rel="noopener noreferrer">{{ link[0] }}</a>{% endfor %}
        </div>
        {% endif %}
      </div>
    </li>
  {% endfor %}
  </ol>
{% endfor %}
</div>
