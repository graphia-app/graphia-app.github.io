## User Guide

## Introduction to Graphs

[Introduction to Graphs]({{site.url}}/guide/graph_introduction.html)

{% assign pages = site.pages | where_exp: "item", "item.url contains 'section1'" %}
{% for entry in site.pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}

## Using Graphia - Getting Started

{% for entry in site.pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}

## Graph-based Data
## Correlation Network Analysis
## Other Useful Information

{% for entry in site.pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
</ul>
