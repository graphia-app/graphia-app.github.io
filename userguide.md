## User Guide

## Introduction to Graphs

[Introduction to Graphs]({{site.url}}/guide/graph_introduction.html)



## Using Graphia - Getting Started
## Graph-based Data
## Correlation Network Analysis
## Other Useful Information

{% assign atopics = site.topic-a | sort: 'order' %}
{% for atopic in atopics %}
  <li {% if page.url == atopic.url %} class="active"{% endif %}>
    <a href="{{ atopic.url }}">{{ atopic.title }}</a>
  </li>
{% endfor %}
</ul>
