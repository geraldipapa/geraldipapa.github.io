---
layout: archive
title: "Research"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign jmp_papers = site.publications | where_exp: "item", "item.jmp == true" %}
{% if jmp_papers.size > 0 %}
## Job Market Paper
{% for post in jmp_papers %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign published = site.publications | where_exp: "item", "item.venue != 'Working Paper'" | where_exp: "item", "item.venue != 'Work in Progress'" %}
{% if published.size > 0 %}
## Publications
{% for post in published reversed %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign working = site.publications | where_exp: "item", "item.venue == 'Working Paper'" | where_exp: "item", "item.jmp != true" %}
{% if working.size > 0 %}
## Working Papers
{% for post in working reversed %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% assign wip = site.publications | where_exp: "item", "item.venue == 'Work in Progress'" %}
{% if wip.size > 0 %}
## Work in Progress
{% for post in wip %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}
