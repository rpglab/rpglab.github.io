---
layout: paper
title: "Deep Neural Network-Enhanced Frequency-Constrained Optimal Power Flow with Multi-Governor Dynamics"
image: 
authors: Fan Jiang, Xingpeng Li, Pascal Van Hentenryck.
year: 2026
ref: Fan Jiang et al, arXiv, 2026. 
journal: "arXiv"
pdf: 
webpdf: https://arxiv.org/pdf/2602.11063
codes: 
doi: 
arxiv: https://arxiv.org/abs/2602.11063
---

# Abstract
To ensure frequency security in power systems, both the rate of change of frequency (RoCoF) and the frequency nadir (FN) must be explicitly accounted for in real-time frequency-constrained optimal power flow (FCOPF). However, accurately modeling system frequency dynamics through analytical formulations is challenging due to their inherent nonlinearity and complexity. To address this issue, deep neural networks (DNNs) are utilized to capture the nonlinear mapping between system operating conditions and key frequency performance metrics. In this paper, a DNN-based frequency prediction model is developed and trained using the high-fidelity time-domain simulation data generated in PSCAD/EMTDC. The trained DNN is subsequently transformed into an equivalent mixed-integer linear programming (MILP) form and embedded into the FCOPF problem as additional constraints to explicitly enforce frequency security, leading to the proposed DNN-FCOPF formulation. For benchmarking, two alternative models are considered: a conventional optimal power flow without frequency constraints and a linearized FCOPF incorporating system-level RoCoF and FN constraints. The effectiveness of the proposed method is demonstrated by comparing the solutions of these three models through extensive PSCAD/EMTDC time-domain simulations under various loading scenarios.

# Index Terms
Deep neural network, frequency nadir, grid synchronous inertia, optimal power flow, rate of change of frequency, real-time economic dispatch, system frequency response. 

# Cite this paper:
Fan Jiang, Xingpeng Li, and Pascal Van Hentenryck, “Deep Neural Network-Enhanced Frequency-Constrained Optimal Power Flow with Multi-Governor Dynamics”, *arXiv*, Feb. 2026.

