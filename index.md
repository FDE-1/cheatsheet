---
title: Cheatsheet Python
layout: default
---

## Leetcode-Patterns
{% for page in site.collections['leetcode-patterns'] %}
  {% if page.url != '/index.html' and page.url != 'readme.html' and page.title%}
  - [{{ page.title }}]({{ page.url | relative_url }})
  {% endif %}
{% endfor %}

## Structures
{% for page in site.collections['structures']%}
  {% if page.url != '/index.html' and page.url != 'readme.html' and page.title%}
  - [{{ page.title }}]({{ page.url | relative_url }})
  {% endif %}
{% endfor %}