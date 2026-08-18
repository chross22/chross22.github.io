---
layout: page
title: "Code and data"
permalink: /code/
lede: "Open-source R packages behind the modelling work — survey ingest through to publication figures."
redirect_from:
  - /portfolio/
---

Most of my analysis lives in small, single-purpose R packages rather than in one
monolithic script. Each does one part of the chain — read the survey archive, build
the covariates, fit the model, draw the figure — so that a study is a short script
over well-tested pieces instead of a thousand lines nobody can re-run. All of the
below are public.

{% assign groups = site.data.software | group_by: "group" %}
{% for g in groups %}
## {{ g.name }}

{% for pkg in g.items %}
<div class="pkg">
  <div class="pkg__name">
    <a href="{{ pkg.repo }}">{{ pkg.name }}</a>
    <span class="pkg__lang">{{ pkg.language }}</span>
  </div>
  <p>{{ pkg.summary }}</p>
  <div class="btn-row mt-5">
    <a class="btn" href="{{ pkg.repo }}">{% include icon.html name="github" %} Repository</a>
    {%- if pkg.paper %}<a class="btn" href="{{ pkg.paper | relative_url }}">{% include icon.html name="doc" %} Related paper</a>{% endif %}
  </div>
</div>
{% endfor %}
{% endfor %}

## Skills

R · Python · MATLAB · Java · git · bash / Unix shell · Linux · SQL · ArcGIS ·
R Shiny · Leaflet · JAGS · targets pipelines
