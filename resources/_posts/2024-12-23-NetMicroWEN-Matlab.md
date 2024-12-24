---
layout: resource
title: Centralized Networked Micro Water-Energy Nexus in Matlab
authors: Jesus Silva-Rodriguez
type: Matlab Code
zip: 
timeInit: 2024-12-23
time: 2024-12-23
github: https://github.com/rpglab/CentralizedNetMicroWEN
paper: /papers/JesusSilvaR-CN-MWEN-PEA/
link: 
doi: 
description: "This is for our NAPS paper: *Centralized Networked Micro Water-Energy Nexus with Proportional Exchange Among Participants*. It implemented both sequential & centralized optmztn for a network of multiple water-energy nexuses."
---

This set of codes/data implements our NAPS paper "Centralized Networked Micro Water-Energy Nexus with Proportional Exchange Among Participants". 

It implemented both (i) benchmark method that solves individual Micro Water-Energy Nexus (MWEN) optimization sequentially, and (ii) a centralized co-optimization model, for a network of multiple MWEN systems.


## Matlab Codes:
Both NetMicroWEN.m codes call the functions SolarIR.m, SolarPow.m, and WindPow.m. These function scripts simply implement the solar and wind power calculations from the datasets provided to obtain solar and wind power profiles.

* "Individual_NetMicroWEN.m" is a MATLAB script that executes the individual optimization of single microWEN in the network, as if they were not interconnected with each other. This is the benchmark to be compared with the centralized network operation to analyze economic benefits.

* "Central_NetMicroWEN.m" implements the centralized optimization of all microWEN systems participating in the network. The code also implements the Proportional Exchange Algorithm (PEA) as a post-processing step once the centralized optimization is complete.

GRID.mat includes a single vector variable containing a 24-hour grid price profile. If a different profile wishes to be introduced, then it must be generated saving a column vector of 24 elements named 'Grid', and of course the .mat file named 'GRID.mat'.


## Citation:
If you use any of our codes/data for your work, please cite the following papers as your reference:

Jesus Silva-Rodriguez and Xingpeng Li, “Centralized Networked Micro Water-Energy Nexus with Proportional Exchange Among Participants”, *54th North American Power Symposium*, Salt Lake City, UT, USA, Oct. 2022.

Paper website: <a class="off" href="/papers/JesusSilvaR-CN-MWEN-PEA/"  target="_blank">https://rpglab.github.io/papers/JesusSilvaR-CN-MWEN-PEA/</a>


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