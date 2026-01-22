---
title: Element Attributes
layout: default
parent: Information Requirements
nav_order: 2
---

# Info. requirements

{% for item in site.data.appendix_b_files %}[{{ item.name }}](#{{ item.name | downcase | replace: " ", "-" | replace: "(", "" | replace: ")", "" }}){% unless forloop.last %} | {% endunless %}{% endfor %}

---

{% for item in site.data.appendix_b_files %}
{% include bimstandarddata/appendix-b/{{ item.file }} %}

{% unless forloop.last %}---{% endunless %}

{% endfor %}
