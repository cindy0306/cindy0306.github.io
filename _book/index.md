---
layout: default
title: "Book"
description: 독서 기록 공간 📚
main: true
project-header: true
# header-img: img/about.jpg
---

<ul class="catalogue">
{% assign sorted = site.book | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.blog == true %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>