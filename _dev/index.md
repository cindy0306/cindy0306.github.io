---
layout: default
title: "Dev"
description: 개발기록 📝
main: true
project-header: true
# header-img: img/about.jpg
---

<ul class="catalogue">
{% assign sorted = site.dev | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.blog == true %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>