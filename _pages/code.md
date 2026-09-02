---
layout: page
title: "Code"
permalink: /code/
lede: "Public R packages, installable and documented. Each runs on any dataset in the documented shape — not only mine."
redirect_from:
  - /portfolio/
---

All of these install from GitHub and run on other people's data — none hard-code
my study system. Each does one part of the chain: read the survey archive, build
the covariates, fit the model, draw the figure.

```r
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
  {%- if pkg.example %}
  <div class="pkg__demo">
    <div class="pkg__code">{% highlight r %}{{ pkg.example }}{% endhighlight %}</div>
    {%- if pkg.schematic %}{% include schematic.html kind=pkg.schematic %}{% endif %}
  </div>
  {%- endif %}
  <div class="btn-row mt-5">
    <a class="btn" href="{{ pkg.repo }}">{% include icon.html name="github" %} Repository</a>
    {%- if pkg.docs %}<a class="btn" href="{{ pkg.docs }}">{% include icon.html name="link" %} Reference</a>{% endif %}
    {%- if pkg.paper %}<a class="btn" href="{{ pkg.paper | relative_url }}">{% include icon.html name="doc" %} Related paper</a>{% endif %}
  </div>
</div>
{% endfor %}
{% endfor %}

## Skills

**Expertise:** R · Python · git · bash / Unix shell · Linux
**Experience:** MATLAB · Java · ArcGIS · R Shiny · Leaflet
**Limited experience:** JavaScript · HTML · CSS · SQL
