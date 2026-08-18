---
layout: page
title: "Code and data"
permalink: /code/
lede: "Open-source, installable R packages — general-purpose tools, not project scripts. Each is documented and works on any dataset in the right shape, not only mine."
redirect_from:
  - /portfolio/
---

Most of my analysis lives in small, single-purpose R packages rather than in one
monolithic script. Each does one part of the chain — read the survey archive, build
the covariates, fit the model, draw the figure — so that a study is a short script
over well-tested pieces instead of a thousand lines nobody can re-run.

**Every package below is public, installable, and written to run on other people's
data.** None of them hard-code my study system: give them data in the documented
shape and they work on any survey, region, or species. Install any of them straight
from GitHub:

```r
install.packages("remotes")
remotes::install_github("chross22/taupatch")
```

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
  <p class="pkg__install"><code>remotes::install_github("chross22/{{ pkg.name }}")</code></p>
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
