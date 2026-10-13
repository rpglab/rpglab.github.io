---
layout: resource
title: ReLU Linearization for NN-Embedded Microgrid Energy Scheduling in Python
authors: Cunzhi Zhao, Fan Jiang
type: Python Code
zip: 
timeInit: 2026-10-12
time: 2026-10-12
github: https://github.com/rpglab/ReLU-Linearization_NN-Embedded-Optimization
paper: /papers/Cunzhi-ReLU-Lin-NNOPT/
link: 
doi: 10.1016/j.segan.2026.102488
description: "This is for our SEGN paper: *Linearization of ReLU Activation Function for Neural Network-Embedded Optimization: Optimal Day-Ahead Energy Scheduling*. It implements 4 ReLU linearization methods (BPWL, CTAR, P-CTAR, and PCAR) for NN-embedded microgrid day-ahead energy scheduling."
---


This set of codes/data implements our SEGN paper "Linearization of ReLU Activation Function for Neural Network-Embedded Optimization: Optimal Day-Ahead Energy Scheduling". It provides 4 ReLU linearization methods (BPWL, CTAR, P-CTAR, and PCAR) for neural network-embedded optimization, demonstrated on microgrid day-ahead energy scheduling with a neural network-based battery degradation (NNBD) model. 


### Linearization Methods
Each method replaces the ReLU activation function with a set of linear constraints, so the NN-embedded scheduling problem becomes a mixed-integer linear program.

| Method | Program | Description |
| --- | --- | --- |
| BPWL: Big-M based piecewise linearization | `SCUC_Linearization_BigM.py` | Exact reformulation of ReLU; adds one binary variable per ReLU neuron. |
| CTAR: convex triangle area relaxation | `SCUC_Linearization_M2.py` | Linear relaxation bounded by the neuron pre-activation lower/upper bounds (LB/UB); no extra binary variables. |
| P-CTAR: penalized CTAR | `SCUC_Linearization_M3.py` | CTAR plus a penalty term in the objective that drives each activation toward its ReLU value. |
| PCAR: penalized convex area relaxation | `SCUC_Linearization_M4.py` | Penalty term only, without the LB/UB constraint; fewest constraints. |

In the paper's microgrid testbed, BPWL is exact but the slowest, while P-CTAR gives the best accuracy-speed trade-off among the three relaxation methods. The Big-M value (M = 100 in the paper) and the penalty constant (c<sub>h</sub> = 10 for P-CTAR in the paper) are problem-specific and should be re-tuned when the optimization model or the neural network changes.


### File Description
* The four programs above can be applied to either a one-layer or a two-layer NNBD model when the network dimensions, weights, biases, bounds, checkpoint, and `.dat` file are changed together. The current root programs are configured for the two-layer model in `trained_nn_1d.pt` and `case17.dat`.
* `case17.dat` contains the 24-hour microgrid data and the NN weights and biases.
* `trained_nn_1d.pt` is the trained two-layer NNBD checkpoint (5 inputs, two ReLU hidden layers with 20 and 10 neurons, and 1 output) used by all four root SCUC programs. `nn_class.py` defines its architecture, and `NN_weights.py` extracts its weights and biases. The values stored in `case17.dat` match this checkpoint, apart from decimal rounding.
* `OneLayer/` contains the one-layer NNBD model used for comparison with the two-layer model; both models can be applied in the four SCUC programs.
* `OneLayer/SCUC_Linearization_BigM_1Layer.py` is the BPWL scheduling test for the one-layer NNBD model. It directly uses `case1layer.dat` as the data file, whose weights and biases are obtained from `trained_DNN.pt` by applying `NN_weights.py`, while `nn_class.py` defines the model class.


### Environment (Python packages)
* Python 3
* pandas
* numpy
* pyomo
* torch
* matplotlib
* scikit-learn
* xlrd
* gurobi (solver)


## Citation:
If you use any of our codes/data for your work, please cite the following paper as your reference:

Cunzhi Zhao, Fan Jiang, and Xingpeng Li, “Linearization of ReLU Activation Function for Neural Network-Embedded Optimization: Optimal Day-Ahead Energy Scheduling”, *Sustainable Energy, Grids and Networks*, vol. 47, article 102488, Aug. 2026.

DOI: <a class="off" href="https://doi.org/10.1016/j.segan.2026.102488"  target="_blank">10.1016/j.segan.2026.102488</a>

Paper website: <a class="off" href="/papers/Cunzhi-ReLU-Lin-NNOPT/"  target="_blank">https://rpglab.github.io/papers/Cunzhi-ReLU-Lin-NNOPT/</a>


## Contributions:
Cunzhi Zhao and Fan Jiang developed the original program. Xingpeng Li supervised this work.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

