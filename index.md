---
title: Cheatsheet Python
layout: default
---

DEBUG: {{ site.collections | size }} collections trouvées
{% for col in site.collections %}
- nom = "{{ col.label }}" / nb docs = {{ col.docs | size }}
{% endfor %}
## Leetcode-Patterns
{% for page in site.collections['_algos'].docs %}
  {% if page.url != '/index.html' and page.url != 'readme.html' and page.title%}
  - [{{ page.title }}]({{ page.url | relative_url }})
  {% endif %}
{% endfor %}

## Structures
{% for page in site.structures %}
  {% if page.url != '/index.html' and page.url != 'readme.html' and page.title%}
  - [{{ page.title }}]({{ page.url | relative_url }})
  {% endif %}
{% endfor %}