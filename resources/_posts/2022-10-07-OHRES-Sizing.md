---
layout: resource
title: Optimal Sizing of Offshore Hybrid Renewable Energy Systems in Python
authors: Cunzhi Zhao
type: Python Code
zip: 
timeInit: 2022-10-07
time: 2022-10-07
github: https://github.com/rpglab/OHRES_sizing
paper: /papers/Cunzhi-OffshoreMG-Sizing/
link: 
doi: 
description: "This is for our NAPS paper: *A 100% Renewable Energy System: Enabling Zero CO2 Emission Offshore Platforms*. It solves the optimal energy resource sizing problem for offshore hybrid renewable energy systems."
---


## Optimal Sizing of Offshore Hybrid Renewable Energy Systems

This program models the zeros emmision resilient offshore hybrid renewable energy system (OHRES). It is designed to optimize the size of the renewable units such that the relavent cost is minimized while meeting various constraints and requirements.


### Input files:
case16.dat
* Case16 includes the load profile for 50MW offshore platform and the wind profile in a typical day at Gulf of Mexico. 


### Codes: 
1. sizing.py  
	* models the BESS, HESS and Wind turbine system.
	* models the resilience duration time when there is no wind power.
2. sensitivity.py   
	* perform the sensitivity tests on the renewable units' prices.
	* based on the sizing.py


### Environment Setting:
To be able to run the code successfully, a python pyomo package and "Gurobi" solver are required.


## Citation:
If you use these codes for your work, please cite the following paper:

Cunzhi Zhao and Xingpeng Li, “A 100% Renewable Energy System: Enabling Zero CO2 Emission Offshore Platforms”, *54th North American Power Symposium*, Salt Lake City, UT, USA, Oct. 2022.

Paper website: <a class="off" href="/papers/Cunzhi-OffshoreMG-Sizing/"  target="_blank">https://rpglab.github.io/papers/Cunzhi-OffshoreMG-Sizing/</a>


## Contributions:
Cunzhi Zhao developed this program. Xingpeng Li supervised this work.


## Contact:
If you need any techinical support, please feel free to reach out to <a class="" href="/people/Cunzhi-Zhao/" target="_blank">Cunzhi Zhao</a> at czhao20@uh.edu.

For collaboration, please contact <a class="" href="/people/Xingpeng-Li/" target="_blank">Dr. Xingpeng Li</a> at xli83@central.uh.edu.

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.
