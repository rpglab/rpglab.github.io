---
layout: paper
title: "Inertia-Constrained Generation Scheduling: Sample Selection, Learning-Embedded Optimization Modeling, and Computational Enhancement"
image: 
authors: Mingjian Tuo, Fan Jiang, Xingpeng Li, Pascal Van Hentenryck.
year: 2025
ref: Mingjian Tuo, Fan Jiang et al, IEEE Transactions on Power Systems, 2025.
journal: "IEEE Transactions on Power Systems"
pdf: 
webpdf: https://arxiv.org/pdf/2307.04880
codes: 
data: /resources/FCUC-24bus-Sys_PSSE-TimeDmn-Data/
doi: 10.1109/TPWRS.2025.3639407
arxiv: https://arxiv.org/abs/2307.04880
---

# Abstract
Day-ahead generation scheduling is conducted by solving securi-ty-constrained unit commitment (SCUC) problem. Fast-growing inverter-based resources dramatically reduce grid inertia, com-promising system dynamic stability. Traditional SCUC (T-SCUC), without any inertia requirements, may no longer be effective for renewables-dominated grids. To address this, we propose the active linearized sparse neural network-embedded SCUC (ALSNN-SCUC) model, utilizing machine learning (ML) to incorporate system dynamic performance. A multi-output deep neural network (DNN) model is trained offline on strategi-cally-selected data samples to accurately predict frequency sta-bility metrics: locational RoCoF and frequency nadir. Struc-tured sparsity and active ReLU linearization are implemented to prune redundant DNN neurons, significantly reducing its size while ensuring prediction accuracy even at high sparsity levels. By embedding this ML-based frequency stability predictor into SCUC as constraints, the proposed ALSNN-SCUC model mini-mizes its computational complexity while ensuring frequency stability following G-1 contingency. Case studies show the pro-posed ALSNN-SCUC can enforce pre-specified frequency re-quirements without being overly conservative, outperforming five benchmark models including T-SCUC, two physics-based SCUC, and two ML-based SCUC. The proposed sparsification and active linearization strategies can reduce the DNN-SCUC computing time by over 95% for both IEEE 24-bus and 118-bus systems, demonstrating the effectiveness and scalability of the proposed ALSNN-SCUC model.

# Index Terms
Deep learning, Frequency deviation, Frequency stability, Line-arization, Low-inertia power systems, Sparse neural network, Rate of change of frequency, Unit commitment

# Cite this paper:
Mingjian Tuo, Fan Jiang, Xingpeng Li, and Pascal Van Hentenryck, “Inertia-Constrained Generation Scheduling: Sample Selection, Learning-Embedded Optimization Modeling, and Computational Enhancement”, *IEEE Transactions on Power Systems*, Dec. 2025.
