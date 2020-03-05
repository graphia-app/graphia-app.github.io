---
title: User Guide
---
## Introduction to Graphs
{% assign pages = site.pages | where_exp: "item", "item.url contains 'section1'" %}
{% for entry in pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}

## Graphia - Getting Started
{% assign pages = site.pages | where_exp: "item", "item.url contains 'section2'" %}
{% for entry in pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}

## Graphia - Graph Analysis
{% assign pages = site.pages | where_exp: "item", "item.url contains 'section3'" %}
{% for entry in pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}

## Graphia - Correlation Network Analysis (Numerical Data)
{% assign pages = site.pages | where_exp: "item", "item.url contains 'section4'" %}
{% for entry in pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
