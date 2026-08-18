---
layout: page
title: "Media"
permalink: /media/
lede: "Interviews, features, and press coverage of the research."
---

{% assign items = site.data.media | sort: "date" | reverse %}
{% for m in items %}
<div class="entry">
  <div class="entry__title">
    {%- if m.url and m.url != "" -%}
      <a href="{{ m.url }}">{{ m.title }}</a>
    {%- else -%}
      {{ m.title }}
    {%- endif -%}
  </div>
  <div class="entry__meta">
    <span class="entry__kind">{{ m.kind }}</span>
    <span class="media__outlet">{{ m.outlet }}</span>
    {%- if m.note %} · {{ m.note }}{% endif -%}
    · {{ m.date | date: "%B %Y" }}
  </div>
</div>
{% endfor %}
