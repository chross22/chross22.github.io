---
layout: page
title: "Media"
permalink: /media/
lede: "Interviews, features, and press coverage of the research."
---

{%- comment -%} One reverse-chronological list. Splitting this into
Interviews/Features buried the newest and most prominent coverage below six
older interviews — and the kind is already tagged on every row, so the split
bought nothing. Same rule as the other list pages: newest first, date inline.
{%- endcomment -%}
{%- assign all = site.data.media | sort: "date" | reverse -%}
{%- assign pinned = all | where: "pin", true -%}
{%- assign rest = all | where_exp: "m", "m.pin != true" -%}
{%- assign items = pinned | concat: rest -%}
{%- for m in items %}
<div class="entry">
  <div class="entry__title">{% if m.url and m.url != "" %}<a href="{{ m.url }}">{{ m.title }}</a>{% else %}{{ m.title }}{% endif %}</div>
  <div class="entry__meta"><span class="entry__kind">{{ m.kind }}</span>{{ m.outlet }}{% if m.note %} · {{ m.note }}{% endif %} · {{ m.date | date: "%B %Y" }}</div>
</div>
{%- endfor %}
