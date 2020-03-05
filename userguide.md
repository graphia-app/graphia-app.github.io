## User Guide

## Introduction to Graphs

[Introduction to Graphs]({{site.url}}/guide/graph_introduction.html)



## Using Graphia - Getting Started
## Graph-based Data
## Correlation Network Analysis
## Other Useful Information

{% assign section = site.section1 %}
{{ site.section1 }}
{% for entry in section %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}
</ul>
