---
title: Authors
published: false
redirect: 'taxonomy?name=author'
process:
    twig: true
    markdown: false
twig_first: true
cache_enable: false
content:
    items: '@self.children'
---

<h1>Authors</h1>
<ul>
{% for p in page.collection %}
    <li><a href="{{ p.url }}">{{ p.title }}</a></li>
{% endfor %}
</ul>

