---
layout: page
title: "Research"
permalink: /research/
lede: "Estimating ecological fields from sparse, irregular, effort-limited observations — and keeping the observation process separate from the ecological one."
---

Our knowledge of whales at sea is contingent upon our ability to find them: whether visually from an airlane or vessel or acoustically from hydrophones. Both of those observation types are shaped as much by the survey as by the animal's behavior and environmental conditions.

My work as a marine ecologist focused on conservation considers what we can infer from the data we are able to collect. I build models that separate the observation process from
the ecological process, so that what comes out the other end is an estimate of what is
actually there rather than an estimate of where we happened to look. That matters
because these models are not academic exercises: they feed directly into the decision
support tools used to manage the critically endangered North Atlantic right whale.

## Where the food is {#prey}

Right whales eat copepods — primarily *Calanus finmarchicus* — and they are extremely
particular about it. A whale does not respond to average copepod abundance; it responds
to whether a patch is dense enough that feeding on it returns more energy than it costs.
That distinction turns out to matter enormously for modelling.

So rather than model copepod abundance and hope it stands in for prey, I model the
environmental conditions associated with aggregations that *exceed a feeding threshold* —
what we call τ-patches. These behave differently from abundance-based models: they favour
a warmer temperature range and show much higher spatial variability. Extending the
approach past *C. finmarchicus* to *Centropages typicus* and *Pseudocalanus* spp. showed
that the prey base is an assemblage that shifts across space and time, not a single
species.

**Key papers:**
[Estimating right whale prey based on *Calanus finmarchicus* thresholds]({{ '/publication/2023-01-12-calanus-finmarchicus-thresholds' | relative_url }}) ·
[Beyond *Calanus*: changes to the copepod community]({{ '/publication/2025-01-09-beyond-calanus-copepod-community' | relative_url }}) ·
[*Calanus* prey and foraging habitat in Canadian waters]({{ '/publication/2024-08-01-calanus-energetics-foraging-habitat-models' | relative_url }})

**Code:** [`taupatch`](https://github.com/chross22/taupatch) implements the threshold
patch models; [`datamatch`](https://github.com/chross22/datamatch) and
[`derivoce`](https://github.com/chross22/derivoce) build the environmental covariates.

## Where the whales are {#density}

Density surface models turn line-transect survey data into maps of animal density. They
are only as good as their treatment of the observation process: how detectability falls
off with distance, how effort is distributed, how much of the variance in a map is
survey design rather than biology.

The question I have spent the most time on is what goes in as a prey covariate. The
convention is chlorophyll concentration — cheap, satellite-derived, and several steps
removed from anything a whale eats. Substituting tailored prey fields for that proxy
improves predicted distributions: the best-performing model combined all three copepod
prey fields and put density where right whales actually are, concentrated in the deep
basins of the Gulf of Maine and the Great South Channel, rising through the summer.

The corollary is a claim about monitoring, not just modelling. Prey fields only exist if
somebody keeps sampling zooplankton.

**Key papers:**
[Incorporating prey fields into right whale density surface models]({{ '/publication/2025-09-11-prey-fields-density-surface-models' | relative_url }}) ·
[Impacts of an oceanographic regime shift on U.S. right whale density estimates]({{ '/publication/2026-regime-shift-right-whale-density-estimates' | relative_url }}) *(in review)*

**Code:** [`narwcr`](https://github.com/chross22/narwcr) and
[`distsamp`](https://github.com/chross22/distsamp) handle survey ingest and segmentation;
[`dsfit`](https://github.com/chross22/dsfit) fits and compares detection functions on
effective strip half-width rather than the Akaike information criterion alone.

## Where both are going {#change}

The Gulf of Maine is one of the fastest-warming pieces of ocean on the planet, and right
whales have already redistributed in ways that broke the assumptions behind existing
management areas. Projecting habitat suitability forward under climate scenarios suggests
the trend continues: declining suitability across much of the Gulf of Maine from mid-summer
into autumn, with a north-eastward shift toward the Scotian Shelf, the Bay of Fundy, and the
Newfoundland and Labrador shelves — much of it outside where conservation effort is
currently concentrated.

Change of that kind is not only gradual. The Gulf of Maine has a documented history of
oceanographic *surprises*, and they have been arriving more often than the long-term trends
alone would predict. That raises a harder question than "what will the mean look like in
2050": what happens to a density estimate built across a regime shift, when the relationship
the model learned no longer holds? That question is the current work.

**Key papers:**
[Projecting right whale habitat suitability for 2050]({{ '/publication/2021-04-28-projecting-right-whale-habitat-2050' | relative_url }}) ·
[Foraging habitat under future climate scenarios]({{ '/publication/2025-05-20-right-whale-foraging-habitat-climate' | relative_url }}) ·
[The surprising oceanography of the Gulf of Maine]({{ '/publication/2023-01-01-gulf-of-maine-oceanography' | relative_url }})

## Methods and tools

- **Observation process** — detectability modelling from line-transect data, density
  surface models with explicit treatment of survey effort, propagating observation
  uncertainty into management-facing estimates
- **Statistical learning** — generalized additive models, boosted regression trees,
  random forests, artificial neural networks (including CNNs trained from scratch)
- **Time series** — spectral analysis of multi-decadal oceanographic and biological series:
  Fourier transforms and periodograms, coherence, filtering, autocorrelation structure
- **Data sources** — Copernicus Marine and NASA EarthData products, ocean physics model
  output (HYCOM, GLORYS, FVCOM, DFO internal models), aerial and vessel survey archives,
  passive acoustic monitoring
- **Practice** — R, Python, git, bash, Linux; reproducible pipelines; R Shiny and Leaflet

<!-- FIGURES: drop 2–3 exported maps into images/research/ and add them here, e.g.
     ![Predicted right whale density, Gulf of Maine](/images/research/density.png)
     Each needs alt text describing what the map shows, not "Figure 1". -->
