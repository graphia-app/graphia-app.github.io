---
title: Wiki Pages
---
## Graphia Wiki Pages
{% assign pages = site.pages | where_exp: "item", "item.url contains 'wiki'" %}
{% for entry in pages %}
  <li>
    <a href="{{ entry.url }}">{{ entry.title }}</a>
  </li>
{% endfor %}