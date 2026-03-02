---
layout: paper
title: "A Two-Stage Hierarchical GNN for Computationally Efficient Reduced Optimal Power Flow"
image: 
authors: Linhan Fang, Thuan Pham, Xingpeng Li.
year: 2026
ref: Linhan Fang et al, arXiv, 2026.
journal: "arXiv"
pdf: 
webpdf: 
doi: 
arxiv: 
---

# Abstract
Power system networks are often modeled as homogeneous graphs, which limits the ability of graph neural network (GNN) to capture individual generator features at the same nodes. By introducing the proposed virtual node-splitting strategy, generator-level attributes like costs, limits, and ramp rates can be fully captured by GNN models, improving GNN’s learning capacity and prediction accuracy. Optimal power flow (OPF) problem is used for real-time grid operations. Limited timeframe motivates studies to create size-reduced OPF (ROPF) models to relieve the computational complexity. In this paper, with virtual node-splitting, a novel two-stage adaptive hierarchical GNN is developed to (i) predict critical monitor lines that would be congested, and then (ii) predict base generators that would operate at the maximum capacity. This will substantially reduce the constraints and variables associated with lines (L) and generators (G) needed for OPF, creating the proposed ROPFLG model. The fundamental reason for the accelerated computation is analyzed by examining the sparse transformation of the constraint matrix of the reduced OPF. Case studies show that the proposed ROPFLG consistently outperforms the benchmark full OPF (FOPF) and the other two ROPF methods in both IEEE 24-bus and TX-123BT system, achieving significant computational time savings while reliably finding optimal solutions.

# Index Terms
Constraint matrix, Economic dispatch, Hierarchical graph neural network, Machine learning, Optimal power flow, Real-time grid operations, Split bus, Transmission network, TX-123BT system, Virtual node.

# Cite this paper:
Linhan Fang, Elias Raffoul, and Xingpeng Li, "A Two-Stage Hierarchical GNN for Computationally Efficient Reduced Optimal Power Flow", *arXiv*, Feb. 2026.
