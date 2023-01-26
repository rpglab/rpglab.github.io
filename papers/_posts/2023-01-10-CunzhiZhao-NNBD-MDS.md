---
layout: paper
title: "Microgrid Optimal Energy Scheduling Considering Neural Network based Battery Degradation"
image: 
authors: Cunzhi Zhao, Xingpeng Li.
year: 2023
ref: Cunzhi Zhao et al, IEEE Transactions on Power Systems, 2023.
journal: "IEEE Transactions on Power Systems"
pdf: 
webpdf: https://arxiv.org/ftp/arxiv/papers/2202/2202.12416.pdf
codes: /resources/MG-EMSwBDNN/
doi: 10.1109/TPWRS.2023.3239113
arxiv: https://arxiv.org/abs/2202.12416
---

# Relevant source codes and datasets
* <a class="" href="/resources/MG-EMSwBDNN/" target="_blank">Python codes: Microgrid Optimal Energy Scheduling with Battery Degradation Neural Network</a>
* <a class="" href="/resources/BDNN-Training-Data/" target="_blank">Dataset and Python Codes for Training a Battery Degradation Neural Network Model</a>
* <a class="" href="/resources/BatryAgingSim-Data/" target="_blank">Dataset and Matlab Simulator for Battery Aging Tests</a>

# Abstract

Battery energy storage system (BESS) can effectively mitigate the uncertainty of variable renewable generation. Degradation is unpreventable and hard to model and predict for batteries such as the most popular Lithium-ion battery (LiB). In this paper, we propose a data driven method to predict the battery degradation per a given scheduled battery operational profile. Particularly, a neural network based battery degradation (NNBD) model is proposed to quantify the battery degradation with inputs of major battery degradation factors. When incorporating the proposed NNBD model into microgrid day-ahead scheduling (MDS), we can establish a battery degradation based MDS (BDMDS) model that can consider the equivalent battery degradation cost precisely with the proposed cycle based battery usage processing (CBUP) method for the NNBD model. Since the proposed NNBD model is highly non-linear and non-convex, BDMDS would be very hard to solve. To address this issue, a neural network and optimization decoupled heuristic (NNODH) algorithm is proposed in this paper to effectively solve this neural network embedded optimization problem. Simulation results demonstrate that the proposed NNODH algorithm is able to obtain the optimal solution with lowest total cost including normal operation cost and battery degradation cost.

# Index Terms
Battery degradation, Battery energy storage system, Energy management system, Machine learning, Microgrid day-ahead scheduling, Neural network, Optimization.

# Cite this paper:
Cunzhi Zhao and Xingpeng Li, “Microgrid Optimal Energy Scheduling Considering Neural Network based Battery Degradation”, *IEEE Transactions on Power Systems*, early access, Jan. 2023.


