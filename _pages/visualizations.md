---
layout: archive
title: "Visualizations"
permalink: /visualizations/
author_profile: true
---

{% include base_path %}


{% for post in site.visualizations reversed %}
  {% include archive-single.html %}
{% endfor %}

