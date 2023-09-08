---
layout: resource
title: Power Grid Real-Time Energy Management System (RT-EMS) software suite 
authors: Xingpeng Li
type: Java Code
zip: 
timeInit: 2023-09-07
time: 2023-09-07
github: 
paper: 
link: 
doi: 
description: "This is a software suite for power grid real-time energy management system. It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules."
---

To be completed...


This is a software suite for power grid real-time energy management system. It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules.


#### Code Structure and Description:
All the source codes are in the folder of src/com. There are six folders as explained below:
* sced: 
	* auxData: implements four sets of sensitivity factors: 
		* power transfer distribution factors (PTDF).
		* line outage distribution factors (LODF).
		* outage transfer distribution factors (OTDF), which is the post-outage PTDF. 
		* transmission switching distribution factors (TSDF).
	* df: converts Matpower format based cases into PSS/E ver30 raw file.
	* gurobi: creates a practical N-1 SCED model following the syntax of Gurobi solver.
	* input: loads data for test power systems and store the raw data.
	* model: creates a power system model that is designed for running SCED. 
	  * Bus-group class is available: given a bus index, it provides information about all components connected to this bus. 
	  * In addition to the power flow data from other classes, it needs to load additional two files for generator cost and generation ramping limit information respectively. 
	  * It supports the lossless model, as well as the lossy model with 5 options for incorporating losses in SCED. 
	  * It can handle multiple variations of both B-theta SCED and PTDF-SCED models. 
	  * The SCED can simulate all contingencies, as well as selected critical contingencies (with all or different selected monitor lines for different contingencies). 
	  * All data can be written into csv files.
	* 
	
	

* rtca_cts:

* casced

* cyberattack:

* powerdata:

* utilxl: 




#### Test System Description:
Six test cases are included here for users' convenience. They are described below:

* IEEE 14-bus test system: this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the link below (in IEEE Common Data Format (ieee14cdf.txt)): https://labs.ece.uw.edu/pstca/pf14/ieee14cdf.txt

* IEEE 39-bus test case (New England system): this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the following reference: G. W. Bills, et.al., "On-Line Stability Analysis Study" RP90-1 Report for the Edison Electric Institute, October 12, 1970, pp. 1-20 - 1-35. prepared by E. M. Gulachenski with New England Electric System and J. M. Undrill with General Electric Co.

* IEEE 118-bus test system: this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the link below (in IEEE Common Data Format (ieee118cdf.txt)): https://labs.ece.uw.edu/pstca/pf118/ieee118cdf.txt

* 2383-bus Polish system: this test case was converted from matpower (https://matpower.org/). The data was provided by Roman Korab (roman.korab@polsl.pl).


## Citation:
If you use any module/data here for your work, please cite the following papers as your references:





## Contributions:



## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

