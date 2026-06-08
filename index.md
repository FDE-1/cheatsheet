---
title: Cheatsheet Python
layout: default
---

{% for page in site.pages %}
  {% if page.url != '/index.html' and page.url != 'readme.html'%}
  - [{{ page.title }}]({{ page.url }})
  {% endif %}
{% endfor %}