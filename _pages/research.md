---
layout: research
title: "Research"
permalink: /research/
lede: "Estimating ecological fields from sparse, irregular, effort-limited observations — and keeping the observation process separate from the ecological one."
editor_options: 
  markdown: 
    wrap: 72
---

Our knowledge of whales at sea is contingent upon our ability to find
them: whether visually from an airplane or vessel or acoustically from
hydrophones. Both of those observation types are shaped as much by the
survey as by the animal's behavior and environmental conditions.

My work as a marine ecologist focused on conservation considers what we
can infer from the data we are able to collect. I build models that
separate the observation process from the ecological process, so that
what comes out the other end is an estimate of what is actually there
rather than an estimate of where we happened to look. That matters
because these models are not academic exercises: they are considered by
the entities who build the tools used to manage the critically
endangered North Atlantic right whale.

## {% include mark.html name="copepod" class="mark--section" %}Whale prey {#prey}

Right whales eat copepods --- primarily *Calanus finmarchicus*. However,
a whale does not necessarily respond to average copepod abundance, but
rather to whether a prey patch is dense enough that feeding on it is
energetically advantageous. That distinction matters especially for
modeling.

Part of my work involves using environmental conditions to explain and
predict prey aggregations that *exceed a whale-specific feeding
threshold*. We refer to these high-density prey aggregations as
τ-patches. This modeling strategy differs from abundance-based models:
we are able to interpolate zooplankton data in a given region, like the
Gulf of Maine, from the perspective of a foraging whale. This led to new
prey covariate fields that have proven useful in right whale density
surface models. The approach has been extended beyond *C. finmarchicus*
to *Centropages typicus* and *Pseudocalanus* spp., revealing that the
τ-patch probability shifts not only between species, but across space
and time.

**Key papers:** [Estimating right whale prey based on *Calanus
finmarchicus*
thresholds](/publication/2023-01-12-calanus-finmarchicus-thresholds)
· [Beyond *Calanus*: changes to the copepod community](/publication/2025-01-09-beyond-calanus-copepod-community) · [*Calanus* prey and foraging habitat in Canadian
waters](/publication/2024-08-01-calanus-energetics-foraging-habitat-models)

**Code:** [`taupatch`](https://github.com/chross22/taupatch) implements
the threshold patch models;
[`datamatch`](https://github.com/chross22/datamatch) and
[`derivoce`](https://github.com/chross22/derivoce) build the
environmental covariates.


<figure class="research-fig">
  <img src="/images/research/prey-taupatch.jpg" alt="Twelve monthly maps of the northeast US shelf and Gulf of Maine, shaded by predicted probability of a high-density Calanus finmarchicus patch. Probability is highest across the Gulf of Maine from May through September and lowest in late autumn and winter." loading="lazy" decoding="async">
  <figcaption>Predicted <em>Calanus finmarchicus</em> &tau;-patches by month, at a threshold of 10,000 individuals m<sup>&minus;2</sup>. <span class="research-fig__cite">From Ross et al. (2023), <i>Marine Ecology Progress Series</i> 703:1&ndash;16. <a href="https://doi.org/10.3354/meps14204">doi.org/10.3354/meps14204</a>. CC BY 4.0.</span></figcaption>
</figure>

## {% include mark.html name="whale" class="mark--section" %}Whale habitat preference {#density}

Density surface models turn systematic line-transect survey data into
maps of animal density. They are only as good as their treatment of the
observation process: how detectability falls off with distance, how
effort is distributed, how much of the variance in a map is survey
design rather than biology.

A central theme of my work has been designing prey covariates and
testing how they can improve endangered species habitat models. Marine
habitat models conventionally rely upon chlorophyll-a concentration or
NPP models as a proxy for zooplankton prey. However, satellite- or
model-derived chlorophyll products are several steps removed from the
food right whales are actually targeting. We have found that
substituting whale-specific prey fields for prey proxies improves right
whale density model distributions: in a recent paper, combining three
right whale-specific copepod prey fields improved density estimates to
closer represent what we would expect in the field.

This work emphasizes the need for continued surveying and sampling of
both whales and zooplankton.

**Key papers:** [Incorporating prey fields into right whale density
surface
models](/publication/2025-09-11-prey-fields-density-surface-models)
· [Impacts of an oceanographic regime shift on U.S. right whale density
estimates](/publication/2026-regime-shift-right-whale-density-estimates)
*(in review)*

**Code:** [`narwcr`](https://github.com/chross22/narwcr) and
[`distsamp`](https://github.com/chross22/distsamp) handle survey ingest
and segmentation; [`dsfit`](https://github.com/chross22/dsfit) fits and
compares detection functions on effective strip half-width rather than
the Akaike information criterion (AIC) alone.


<figure class="research-fig">
  <img src="/images/research/density-change.jpg" alt="Twelve monthly anomaly maps from Cape Hatteras to the Scotian Shelf, showing the change in predicted right whale density when copepod prey fields replace conventional covariates. Red indicates higher predicted density, blue lower; the strongest increases are in April and May." loading="lazy" decoding="async">
  <figcaption>Change in predicted right whale density when all three copepod prey fields are included, against the baseline model. These are anomalies, not absolute density. <span class="research-fig__cite">From Ross et al. (2025), <i>Endangered Species Research</i> 58:67&ndash;84. <a href="https://doi.org/10.3354/esr01435">doi.org/10.3354/esr01435</a>. CC BY 4.0.</span></figcaption>
</figure>

## {% include mark.html name="gulf-map" class="mark--section" %}Looking to the future {#change}

The Gulf of Maine is warming faster than the rest of the ocean, and
right whales have already redistributed in ways that broke the
assumptions behind existing management strategies and surveying designs.
Projecting habitat suitability forward into 2050 under different IPCC
climate scenarios suggests the trend continues: declining suitability
across much of the Gulf of Maine from mid-summer into autumn, with a
north-eastward shift toward the Scotian Shelf, the Bay of Fundy, and the
Newfoundland and Labrador shelves --- much of it outside where
conservation effort has been historically concentrated.

Change of this scale presents on decadal as well as on interannual and
monthly scales. The Gulf of Maine has a documented history of
unprecedented oceanographic conditions, arriving with increasing
frequency than the decadal-scale trends alone would predict. That raises
a harder question than "what will the mean look like in 2050": what
happens to a density estimate built across distinct oceanographic
regimes, when the relationship the model learned no longer holds? This
is the underlying question of much of my current work.

**Key papers:** [Projecting right whale habitat suitability for
2050](/publication/2021-04-28-projecting-right-whale-habitat-2050)
· [Foraging habitat under future climate
scenarios](/publication/2025-05-20-right-whale-foraging-habitat-climate)
· [The surprising oceanography of the Gulf of
Maine](/publication/2023-01-01-gulf-of-maine-oceanography)


<figure class="research-fig">
  <img src="/images/research/habitat-2050.jpg" alt="Twenty-four small maps of the Gulf of Maine showing modelled right whale habitat suitability in the year 2050, arranged in four labelled blocks for July, August, September and October, each under two emissions scenarios and three chlorophyll assumptions. Suitability concentrates along the shelf edge and the eastern Gulf." loading="lazy" decoding="async">
  <figcaption>Year-2050 habitat suitability projections by month, under two emissions scenarios (RCP 4.5 and 8.5) and three chlorophyll assumptions: <strong>HC</strong>, half present-day chlorophyll; <strong>SC</strong>, the same as present day; <strong>DC</strong>, double. Colour is the modelled likelihood of suitable habitat, from 0 to 1. <span class="research-fig__cite">From Ross et al. (2021), <i>Elementa: Science of the Anthropocene</i> 9(1):00058. <a href="https://doi.org/10.1525/elementa.2020.20.00058">doi.org/10.1525/elementa.2020.20.00058</a>. CC BY 4.0.</span></figcaption>
</figure>

## Methods and tools

-   **Observation process** --- detectability modeling from
    line-transect data, density surface models with explicit treatment
    of survey effort, propagating observation uncertainty into
    management-facing estimates
-   **Statistical learning** --- generalized additive models, boosted
    regression trees, random forests, artificial neural networks
    (including CNNs trained from scratch)
-   **Time series** --- spectral analysis of multi-decadal oceanographic
    and biological series: Fourier transforms and periodograms,
    coherence, filtering, autocorrelation structure
-   **Data sources** --- Copernicus Earth Observation and NASA EarthData
    products, ocean physics model output (HYCOM, GLORYS, FVCOM, DFO
    internal models), aerial and vessel survey archives, passive
    acoustic monitoring
-   **Practice** --- R, Python, git, bash, Linux; reproducible
    pipelines; R Shiny and Leaflet

