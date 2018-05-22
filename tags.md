---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
title: Home
navigation_weight: 1
---

{% for p in site.pages %}
- {{p.title}}
  {% for t in p.tags %}
  - {{t}}
  {% endfor %}
{% endfor %}