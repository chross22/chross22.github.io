---
layout: page
title: "Media"
permalink: /media/
lede: "Interviews, features, and press coverage of the research."
---

{%- comment -%} Same shape as the other list pages: named sections, newest
first inside each, date inline on the row. {%- endcomment -%}
{%- assign items = site.data.media | sort: "date" | reverse -%}

{%- assign features = items | where_exp: "m", "m.kind contains 'Feature'" -%}
{%- assign interviews = items | where_exp: "m", "m.kind contains 'interview'" -%}

{%- if interviews.size > 0 %}
<h2 class="year">Interviews</h2>
{%- for m in interviews %}
<div class="entry">
  <div class="entry__title">{% if m.url and m.url != "" %}<a href="{{ m.url }}">{{ m.title }}</a>{% else %}{{ m.title }}{% endif %}</div>
  <div class="entry__meta"><span class="entry__kind">{{ m.kind }}</span>{{ m.outlet }}{% if m.note %} · {{ m.note }}{% endif %} · {{ m.date | date: "%B %Y" }}</div>
</div>
{%- endfor %}
{%- endif %}

{%- if features.size > 0 %}
<h2 class="year">Features</h2>
{%- for m in features %}
<div class="entry">
  <div class="entry__title">{% if m.url and m.url != "" %}<a href="{{ m.url }}">{{ m.title }}</a>{% else %}{{ m.title }}{% endif %}</div>
  <div class="entry__meta"><span class="entry__kind">{{ m.kind }}</span>{{ m.outlet }}{% if m.note %} · {{ m.note }}{% endif %} · {{ m.date | date: "%B %Y" }}</div>
</div>
{%- endfor %}
{%- endif %}
