---
layout: paper
title: "Constraints and Variables Reduction for Optimal Power Flow Using Hierarchical Graph Neural Networks with Virtual Node-Splitting"
image: 
authors: Thuan Pham, Xingpeng Li.
year: 2025
ref: Thuan Pham et al, IEEE IAS Annual Meeting, 2025.
journal: "IEEE IAS Annual Meeting"
pdf: 
webpdf: https://arxiv.org/abs/2411.06268
doi: 10.1109/IAS62731.2025.11061754
arxiv: https://arxiv.org/abs/2411.06268
---

# Abstract
Power system networks are often modeled as homogeneous graphs, which limits the ability of graph neural network (GNN) to capture individual generator features at the same nodes. By introducing the proposed virtual node-splitting strategy, generator-level attributes like costs, limits, and ramp rates can be fully captured by GNN models, improving GNN's learning capacity and prediction accuracy. Optimal power flow (OPF) problem is used for real-time grid operations. Limited timeframe motivates studies to create size-reduced OPF (ROPF) models to relieve the computational complexity. In this paper, with virtual node-splitting, a novel two-stage adaptive hierarchical GNN is developed to (i) predict critical lines that would be congested, and then (ii) predict base generators that would operate at the maximum capacity. This will substantially reduce the constraints and variables needed for OPF, creating the proposed ROPFLG model with reduced monitor lines and reduced generator-specific variables and constraints. Two ROPF models, ROPFL and ROPFG, with just reduced lines or generators respectively, are also implemented as additional benchmark models. Case studies show that the proposed ROPFLG consistently outperforms the benchmark full OPF (FOPF) and the other two ROPF methods, achieving significant computational time savings while reliably finding optimal solutions.


# Index Terms
Economic dispatch, Hierarchical graph neural network, Machine learning, Optimal power flow, Power flow, Virtual node, Split bus, Transmission network.

# Cite this paper:
Thuan Pham and Xingpeng Li, "Constraints and Variables Reduction for Optimal Power Flow Using Hierarchical Graph Neural Networks with Virtual Node-Splitting", *IEEE IAS Annual Meeting*, New Taipei, Jun. 2025.
