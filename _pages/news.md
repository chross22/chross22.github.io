---
layout: page
title: "News"
permalink: /news/
---

{% assign items = site.data.news | sort: "date" | reverse %}
<ul class="news">
{% for item in items %}{% include news-item.html item=item %}{% endfor %}
</ul>
