---
layout: resource
title: Grid Real-Time Operation Simulator (GRTOS) software suite 
authors: Xingpeng Li
type: Java Code
zip: 
timeInit: 2023-09-07
time: 2023-09-07
github: 
paper: 
link: 
doi: 
description: "This is a software suite for power grid real-time energy management system (EMS). It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules."
---


This is a software suite for power grid real-time energy management system (EMS). It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules.


#### Papers from this GRTOS software:
With this software, we were able to publish multiple papers. A subset of milestone papers are provided below:

* Xingpeng Li, Pranavamoorthy Balasubramanian, Mostafa Sahraei-Ardakani, Mojdeh Abdi-Khorsand, Kory W. Hedman, and Robin Podmore, “Real-Time Contingency Analysis with Correct Transmission Switching,” *IEEE Transactions on Power Systems*, vol. 32, no. 4, pp. 2604-2617, Jul. 2017. <a class="" target="_blank" href="/papers/XLI-RTCAwCTS/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhanced Energy Management System with Corrective Transmission Switching Strategy— Part I: Methodology,” *IEEE Transactions on Power Systems*, vol. 34, no. 6, pp. 4490-4502, Nov. 2019. <a class="" target="_blank" href="/papers/XingpengLi-KWH-TPWRS-Part-I/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhanced Energy Management System with Corrective Transmission Switching Strategy— Part II: Results and Discussion,” *IEEE Transactions on Power Systems*, vol. 34, no. 6, pp. 4503-4513, Nov. 2019. <a class="" target="_blank" href="/papers/XingpengLi-KWH-TPWRS-Part-II/">[Link Here]</a>

* Xingpeng Li, Pranavamoorthy Balasubramanian, Mojdeh Abdi-Khorsand, Akshay S. Korad, and Kory W. Hedman, “Effect of Topology Control on System Reliability: TVA Test Case,” *CIGRE US National Committee Grid of the Future Symposium*, Houston, TX, USA, Oct. 2014. <a class="" target="_blank" href="/papers/XLi-ASU-Cigre/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhancing Power System Cyber-Security with Systematic Two-Stage Detection Strategy,” *IEEE Transactions on Power Systems*, vol. 35, no. 2, pp. 1549-1561, Mar. 2020. <a class="" target="_blank" href="/papers/XLI-CyberSecurity/">[Link Here]</a>

* Xingpeng Li, Akshay S. Korad, and Pranavamoorthy Balasubramanian, “Sensitivity Factors based Transmission Network Topology Control for Violation Relief,” *IET Generation, Transmission and Distribution*, vol. 14, no. 17, pp. 3539-3547, Sep. 2020. <a class="" target="_blank" href="/papers/LODF-CTS_IET-GTD/">[Link Here]</a>


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
	* test: two test programs/applications.
	* util: some utility / auxiliary classes, including data input and output interfacing codes.
* powerdata: this folder of codes is from OpenPA (first version) that is an open-source AC power flow tool developed by PowerData Corpration, Incremental Systems Corporation. Their copyright note is included in each of the code file in this folder. Some modifications were made to best interface with other codes for RTCA, TS, and SCED.
* rtca_cts: 
	* contingencyanalysis: implements both sequential and parallel RTCA, as well as relevant features: contingency list, various participation factors for remaining online generators under generator outage, generator VAR limit examination and bus type switch, flow and voltage violations information recording, sets of monitor elements for violation record.
	* transmissionswitching: implements both sequential and parallel corrective TS, as well as relevant features: candidate switching list determination with multiple options, best TS line and violation relief recording.
	* batch: run some application programs over multiple test cases with one 'click'.
	* param: implements classes to manage various parameters for various applications, including PF, RTCA, TS, violation recording, input/output engines, etc.
	* ausXP: some utility / auxiliary classes: bus type switch and manage; calculate the distance (in terms of number of buses in between in the shortest path) between two elements (bus/line); write system data and/or power flow solutions to files. Convert PSS/E .raw file to .csv format outputs.
	* ausData: supporting grid data processing classes to facilitate data retrieval. For 
	  * ACBranchRates: a single point for processing and retrieving ratings and reactance all two-end devices including lines, transformers and phase shifters.
	  * AreaData: area/zone-related data processing functions.
	  * VoltageLevelData: voltage level-related data processing functions.
	  * BusGroupElems: given a bus, provide lists of all elements including both one-end elements and two-end elements.
	  * RadialBranches: provide a list of radial lines, the failure/disconnection of which will lead to network separation. It can also check wheather a given single line is radial or not, to be computationally efficient. It also works for dynamic network topologies.
	  * ElemMapBus: maps elements to buses; provide subsets of buses that connect to a given type of element.
	  * NearbyElems: provides a list of nearby elements.
	  * OneBusIsland: given a bus "aa", only one bus directly connects to it; this bus "aa" is a OneBusIsland Bus.
	  * PowerFlowResults: a separate class to store power flow results. 
* casced: this folders connects multiple EMS modules for an integrated grid real-time operational software.
	* SCEDwCA: connects DC SCED with AC RTCA, SCED solution is examined via post-SCED RTCA (another RTCA run with generator active power outputs from SCED).
	* SCEDwCTS_CA: connects DC SCED with AC RTCA and AC CTS: not completely automated yet; some manual modifications (hard code) may be needed.
* cyberattack: implements a false data injection (FDI) detection (FDID) method. It takes the FDI simulation data (from a different program) as input.
* utilxl: some utility / auxiliary classes, such as logging. A linearized AC power flow (LACPF) class is also included, supporting customized coefficient for the linear LACPF model.


#### Test System Description:
Six test cases are included here for users' convenience. They are described below:

* WSCC 9-Bus System: the data of this test case are from the link below: https://icseg.iti.illinois.edu/wscc-9-bus-system/

* IEEE 14-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee14cdf.txt)): https://labs.ece.uw.edu/pstca/pf14/ieee14cdf.txt

* IEEE 24-bus system: it is one of the three areas of the IEEE 73-bus system explained below. Three versions are provided here.

* IEEE 30-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee30cdf.txt)): https://labs.ece.uw.edu/pstca/pf30/ieee30cdf.txt

* IEEE 39-bus test case (New England system): this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the following reference: G. W. Bills, et.al., "On-Line Stability Analysis Study" RP90-1 Report for the Edison Electric Institute, October 12, 1970, pp. 1-20 - 1-35. prepared by E. M. Gulachenski with New England Electric System and J. M. Undrill with General Electric Co.

* IEEE 57-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee57cdf.txt)): https://labs.ece.uw.edu/pstca/pf57/ieee57cdf.txt

* IEEE 73-bus system: it is described in this reference: "The IEEE Reliability Test System-1996. A report prepared by the Reliability Test System Task Force of the Application of Probability Methods Subcommittee" and link is <a class="" target="_blank" href="https://ieeexplore.ieee.org/document/780914">here</a>. 

* IEEE 118-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee118cdf.txt)): https://labs.ece.uw.edu/pstca/pf118/ieee118cdf.txt

* IEEE 300-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee300cdf.txt)): https://labs.ece.uw.edu/pstca/pf300/pg_tca300bus.htm

* 2383-bus Polish system: the original data are provided by Roman Korab (roman.korab@polsl.pl). Three modified versions are provided here.


#### Input Files:
* input/*.raw: PSS/E raw file (version 29 or 30): power flow data for PF/RTCA/TS.
* input/sced_ver01/*: generator cost and ramping limit information.
* input/FDI_model/*: FDI simulation data for FDID evaluation.
* dataToRead/*: additional data files to read for some specific application programs.
* CpsConfg.ini: the configure file that the program will first read.

#### Output Files:
All output files will be generated in this folder 'filesOfOutput'.




## Acknowledgment and Contributions:



## Citation:
If you use any codes/data here for your work, please cite the relevant papers listed above as your references.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>

(Note that the codes under folder 'src/com/powerdata/*' were developed by PowerData Corpration, Incremental Systems Corporation. They are under a different license: BSD-3-Clause license; their copyright note is provided in each of the code file in this folder.


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

