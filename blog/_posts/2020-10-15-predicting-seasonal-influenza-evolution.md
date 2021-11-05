---
layout: post
title: Predicting seasonal influenza evolution
authors:
  - John Huddleston
  - Pierre Barrat-Charlaix
date: 2020-10-13
---

In this post, we summarize and synthesize the results of our recent efforts to predict influenza evolution as described in [Huddleston et al. 2020](https://doi.org/10.7554/eLife.60067) and [Barrat-Charlaix et al. 2020](https://www.biorxiv.org/content/10.1101/2020.07.31.231100v1).

### Why do we try to predict seasonal influenza evolution?

Seasonal influenza (or "flu") sickens or kills millions of people per year.
Flu vaccines are one of the most effective preventative measures against infection.
However, flu vaccines require almost a year to develop and can only contain a single representative virus per flu lineage (A/H3N2, A/H1N1pdm, B/Victoria, and B/Yamagata).
These limitations require researchers to predict which single current flu virus will be the most representative of the flu population one year in the future.
The better these predictions are, the more likely the vaccine will prevent illness and death from infection.

### How do we think flu evolves?

Flu rapidly accumulates mutations during replication, due to its error-prone RNA polymerase.
For most flu genes, most new amino acid mutations will weaken the functionality of their corresponding proteins and reduce the virus's fitness.
For flu's primary surface proteins, hemagglutinin (HA) and neuraminidase (NA), some amino acid mutations modify binding sites of host antibodies from previous infections.
These mutations increase a virus's fitness by allowing the virus to escape existing antibodies in a process called antigenic drift (Figure 1).
Mutations in HA and NA create fitness trade-offs, where beneficial mutations facilitate antigenic drift against a background of deleterious mutations.
