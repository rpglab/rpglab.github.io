---
layout: resource
title: Water-Energy Co-Optimization with Enhanced OB-ADMM
authors: Jesus Silva-Rodriguez
type: Python Code
zip: 
timeInit: 2024-08-07
time: 2024-08-07
github: https://github.com/rpglab/MWEN_OB-ADMM
paper: /papers/JesusS-Decnt-MicroW-E/
link: 
doi: 
description: "This is for our EPSR paper: *Decentralized Micro Water-Energy Co-optimization for Small Communities*. It implemented the standard ADMM method and the proposed OB-ADMM method."
---

Micro Water-Energy Nexus (MWEN): Small-Scale Water-Energy Distribution Co-Optimization

This set of codes/data implements our EPSR paper "Decentralized Micro Water-Energy Co-optimization for Small Communities". It implemented the standard Alternating Direction Method of Multipliers (ADMM) method and the proposed objective-based ADMM (OB-ADMM) method, which is able to robustly optimize each system independently towards a common objective, only sharing information about the power consumption of water management, providing privacy for each resource provider.


## Python Jupyter Notebook:
Codes are implemented in Python, using Jupyter Notebook. 

* "MEM-MWM_CMWEN.ipynb" is Python notebook which includes blocks of code for the separate optimization of the MEM and MWM models, along with the centralized MWEN model for comparison of the results of separate optimization and combined co-optimization.

* "Decentralized_MWEN.ipynb" is a Python notebook which contains the centralized MWEN model as well as two decentralized approaches to the MWEN problem: via Standard ADMM and Objective-Based ADMM (OB-ADMM).


## Citation:
If you use any of our codes/data for your work, please cite the following papers as your reference:

Jesus Silva-Rodriguez and Xingpeng Li, “Decentralized Micro Water-Energy Co-Optimization for Small Communities”, *Electric Power Systems Research*, vol. 234, 110611, Sep. 2024.

Paper website: <a class="off" href="/papers/JesusS-Decnt-MicroW-E/"  target="_blank">https://rpglab.github.io/papers/JesusS-Decnt-MicroW-E/</a>


## Contributions:
Jesus Silva-Rodriguez developed this set of programs/data. Xingpeng Li supervised this work.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: https://rpglab.github.io/


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.