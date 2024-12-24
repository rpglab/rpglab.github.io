---
layout: resource
title: Water-Energy Co-Optimization Model for a Community-Scale Microgrid in Matlab
authors: Jesus Silva-Rodriguez
type: Matlab Code
zip: 
timeInit: 2024-12-22
time: 2024-12-22
github: https://github.com/rpglab/SingleMicroWEN
paper: /papers/JesusSilvaRodriguez-XLi-WECoOp_CSM/
link: 
doi: 
description: "This is for our NAPS paper: *Water-Energy Co-Optimization for Community-Scale Microgrids*. It implemented a co-optimized model for the two subsystems for supplying the water and energy in a community-scale microgrid."
---

This set of codes/data implements our NAPS paper "Water-Energy Co-Optimization for Community-Scale Microgrids". 

## Matlab Codes:

1. "Open GridData_Processing.m": Load the desired ERCOT LMP prices dataset and execute to obtain GRID.mat: a file containing a MATLAB vector variable with a 24-hr grid price based on the hourly average of LMP for all locations in the file.

2. "Open Parameters.m": Execute to otbtain PARAM.mat: a file containing all MATLAB variables for the parameters of all energy and water input sources (i.e., generators, energy storage, water treatment units, etc.). The program will prompt the selection of the scenario to be analyzed, whether MEM only, MWM only, or the combined WECoOp. 
   Modify the numeric parameters if you wish to input your own test case.
   
3. "Open Water_Energy_Co_Opt.m": Execute to obtain results of the preselected scenario from Parameters.m. This code will load up PARAM.m to obtain energy and water sources parameters and execute the respective optimization model for the preselected scenario. The model outputs the objective value results and plots for every water and energy input source.



## Citation:
If you use any of our codes/data for your work, please cite the following papers as your reference:

Jesus Silva-Rodriguez and Xingpeng Li, “Water-Energy Co-Optimization for Community-Scale Microgrids”, *53rd North American Power Symposium*, College Station, TX, USA, Nov. 2021.

Paper website: <a class="off" href="/papers/JesusSilvaRodriguez-XLi-WECoOp_CSM/"  target="_blank">https://rpglab.github.io/papers/JesusSilvaRodriguez-XLi-WECoOp_CSM/</a>


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