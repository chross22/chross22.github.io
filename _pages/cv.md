---
layout: page
title: "CV"
permalink: /cv/
redirect_from:
  - /resume
actions:
  - text: "Download CV (PDF)"
    url: /files/Camille-Ross-CV.pdf
    icon: download
---

Quantitative biological oceanographer and postdoctoral researcher specializing in the estimation
of ecological fields from sparse, irregular, and effort-limited observations. Eight years
of experience separating the observation process from the ecological process —
detectability, survey effort, and multi-resolution data fusion — in models that directly
inform decision-making around endangered species and environmental management. Skilled in
applied statistical learning and spatiotemporal modeling (R, Python, MATLAB), with repeated
testing of model transferability across new time periods, climate scenarios, and documented
regime shifts.

## Education

**Ph.D. in Oceanography** — University of Maine, Orono, ME · May 2025
Darling Marine Center, School of Marine Sciences
*Dissertation:* Modeling North Atlantic right whales and their prey

**B.A., Environmental Computation** — Colby College, Waterville, ME · May 2020
*Honors thesis:* Projecting regions of North Atlantic right whale, *Eubalaena glacialis*,
habitat suitability in the Gulf of Maine in 2050
*Awards:* Phi Beta Kappa · Magna Cum Laude · Presidential Scholar · Dean's List ·
Environmental Computation Award · Distinction in Environmental Computation ·
Honors in Environmental Studies · Buck Prize for Environmental Writing

**Sea Education Association**, S285: Oceans and Climate — Woods Hole, MA · Spring 2019
*Research project:* Baroclinic instability and zonal fronts along the Chatham Rise, NZ,
and in the southwestern Pacific Ocean

**Bigelow Laboratory for Ocean Sciences**, Sea Change Semester — Fall 2018
*Research project:* Physical factors affecting North Atlantic right whale,
*Eubalaena glacialis*, habitat preference in the Gulf of Maine

## Research and professional experience

**Darling Marine Center, University of Maine**, Walpole, ME · January 2026 – present
In partnership with the Maine Department of Marine Resources, Marine Mammal Research Division.
- *Postdoctoral Research Associate* (full time, June 2026 – present)
- *Research Associate* (contract, January 2026 – June 2026)

Analysis and integration of historical and ongoing datasets of large whales, zooplankton
prey, and oceanographic variables collected under differing survey designs and sampling
frequencies.

**Associate Research Scientist II**, Spatial Ecology, Mapping, Assessment, and
Photogrammetry (EcoMAP) — Anderson Cabot Center for Ocean Life, New England Aquarium,
Boston, MA · January 2024 – January 2026
Analyzed North Atlantic right whale aerial survey data to build density surface models,
modeling detectability and survey effort explicitly alongside the ecological signal.

**Bigelow Laboratory for Ocean Sciences**, East Boothbay, ME · September 2018 – December 2023
- *Research Associate*, Tandy Center for Ocean Forecasting (Jan 2023 – Dec 2023) — tested
  potential improvements to North Atlantic right whale density surface models
- *Research Technician*, Tandy Center for Ocean Forecasting (June 2020 – Jan 2023) — modeled
  right whale prey aggregations in the Gulf of Maine from spatially and temporally patchy
  ship-based sampling
- *Research Intern*, Computational Ecology Lab (July 2019) — species distribution models of
  right whale habitat suitability, present-day and under future climate scenarios
- *Sea Change Semester independent research* (Sept – Dec 2018) — correlation between
  Lagrangian coherent structures and right whale sightings in the Gulf of Maine

**Computer Programming Intern** — Anderson Cabot Center for Ocean Life, New England
Aquarium, Boston, MA · June 2019
Species distribution models of bowhead whales in the Chukchi Sea and North Atlantic right
whales in the Gulf of Maine.

**Research Assistant**, Environmental Studies Department — Colby College, Waterville, ME ·
September 2016 – May 2020
Georeferenced nautical charts in ArcGIS to reconstruct historical kelp coverage in
California; transcribed ICCAT data to track bluefin tuna fishery sustainability; examined
the correlation between farm-to-school programs and sustainable fisheries.

## Computational and field skills

**Observation-process and sampling-design modeling** — detectability modeling from
line-transect survey data; density surface modeling with explicit treatment of survey
effort; quantifying how survey coverage and design constrain achievable inference;
propagation of observation uncertainty into management-facing estimates

**Time series and spectral analysis** — multi-decadal oceanographic and biological time
series; Fourier transforms and periodograms, coherence between series, filtering, and
autocorrelation structure, applied to tidal signal analysis (MATLAB); quantifying the
effect of a documented oceanographic regime shift on model-derived density estimates

**Programming** — expertise in R, Python, git, bash/Unix shell scripting, and Linux;
experience with MATLAB, Java, and ArcGIS; limited experience with JavaScript, HTML,
CSS, and SQL

**Analysis and visualization** — species distribution modeling, density surface modeling,
generalized additive models, large dataset management; training artificial neural networks
from scratch in TensorFlow, including CNNs for image classification, video processing
algorithms, and natural language processing; R Shiny and Leaflet mapping

**Remote sensing and data sources** — satellite-derived oceanographic and climate products
including Copernicus Earth Observation and NASA EarthData (chlorophyll concentration, sea
surface temperature); ocean physics model output (HYCOM, GLORYS, FVCOM, and internal
Fisheries and Oceans Canada models); aerial and vessel survey data; oceanographic
sampling cruises

**Field and sampling methods** — deploying CTD and Niskin rosettes; zooplankton sampling
using bongo nets; marine mammal spotting

**Languages** — English (native); German (CEFR B2, self-assessed); Spanish, Latin
American (CEFR B2, self-assessed)

## Publications

Google Scholar, September 2026: 113 citations · h-index 6 · i10-index 5.

{% assign inreview = site.publications | where: "status", "in-review" | sort: "date" | reverse %}
{% if inreview.size > 0 %}*In review*
{% for p in inreview %}{% include pub-item.html pub=p style="cv" %}{% endfor %}
{% endif %}
{% assign published = site.publications | where_exp: "d", "d.status != 'in-review'" | sort: "date" | reverse %}
{% for p in published %}{% include pub-item.html pub=p style="cv" %}{% endfor %}

## Selected presentations

A full list of {{ site.talks.size }} conference presentations, invited seminars, and
workshops is on the [talks page]({{ '/talks/' | relative_url }}).

{% assign talks = site.talks | sort: "date" | reverse %}
{% for t in talks limit: 8 %}{% include entry-item.html entry=t %}{% endfor %}

## Teaching, mentoring, and outreach

{% assign teaching = site.teaching | sort: "date" | reverse %}
{% for t in teaching %}{% include entry-item.html entry=t %}{% endfor %}

## Media

Selected interviews and features are listed on the [media page]({{ '/media/' | relative_url }}).

## Software

Eight public R packages supporting this work are described on the
[code page]({{ '/code/' | relative_url }}).

## Committees, working groups, and society memberships

- Habitat and Ecosystems Subcommittee Member, Regional Wildlife Science Collaborative for
  Offshore Wind (RWSC) — 2024–present
- North Atlantic Right Whale Transboundary Species Distribution Modeling Working Group —
  2022–present
- Organizing Committee Member, Ocean Hack Week — 2024
- Member, Society for Marine Mammalogy — 2024–present
- Member, Ecological Forecasting Initiative — 2022–present

## References

Available upon request.
