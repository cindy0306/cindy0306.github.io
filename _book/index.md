---
layout: default
title: "Book"
description: 읽었던 책에 대해 제 생각을 기록하는 습관을 길들이기 위한 공간입니다 📚
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
