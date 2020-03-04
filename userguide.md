## User Guide

## Introduction to Graphs

[Introduction to Graphs]({{site.url}}/guide/graph_introduction.html)



## Using Graphia - Getting Started
## Graph-based Data
## Correlation Network Analysis
## Other Useful Information

{% assign section = site.guide-1 %}
{% for entry in section %}
  <li {% if page.url == entry.url %} class="active"{% endif %}>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
</ul>
