---
layout: archive
title: "Updates"
permalink: /updates/
author_profile: true
---

{% include base_path %}


{% for post in site.updates reversed %}
  {% include archive-single.html %}
{% endfor %}

