---
layout: default
title: "Blog"
description: 끄적끄적 일상 이야기 📌
main: true
project-header: true
# header-img: "img/2020.jpeg"
# header-img: img/about.jpg
---

<ul class="catalogue">
{% assign sorted = site.blog | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.blog == true %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>