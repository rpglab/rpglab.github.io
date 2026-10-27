---
layout: paper
title: "A Topology-Aware Neural Network for Fault Location With Missing Measurements"
image: 
authors: Fan Jiang, Linhan Fang, Xingpeng Li, Kaushik Rajashekara.
year: 2026
ref: Fan Jiang, Linhan Fang et al, arXiv, 2026. 
journal: "arXiv"
pdf: 
webpdf: 
codes: 
doi: 
arxiv: 
---

# Abstract
This paper proposes a topology-aware neural network-based fault locator (TANFL) for radial distribution feeders, which uses voltage and current phasors obtained after the decay of fault induced transients, as well as feeder connection relationships and line parameters, as inputs. The shared bus encoder, bus readout module, and gated line readout module work together to identify the faulty bus or line and estimate the continuous fault location on the selected line. During training, explicit missing data indicators and random bus data block masking are introduced, enabling a single trained model to handle both complete measurement sets and scenarios where any permitted bus’s measurement device fails. On the IEEE 15-bus feeder, this paper compares TANFL with a conventional multilayer perceptron (MLP) and the formula-based localization method under identical data, measurement availability scenarios, and evaluation metrics. On the test partition, TANFL outperforms the conventional MLP; with complete measurements, its line fault location performance is slightly lower than that of the formula-based method, but in the average results for scenarios with one missing bus measurement block, its accuracy is the highest among the three methods at a 5% tolerance.

# Index Terms
Distribution systems, Fault location, Missing measurements, Neural networks, Topology-aware learning.

# Cite this paper:
Fan Jiang, Linhan Fang, Xingpeng Li, and Kaushik Rajashekara, “A Topology-Aware Neural Network for Fault Location With Missing Measurements”, *arXiv*, Oct. 2026.

<div class="spacer"></div> 

<div class="smallspacer"></div> ![](/images/papers/2026.10.26_TANFL_FaultLoc.png) 

<div class="spacer"></div>