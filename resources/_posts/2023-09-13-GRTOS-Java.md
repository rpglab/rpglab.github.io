---
layout: resource
title: Grid Real-Time Operation Simulator (GRTOS) software suite 
authors: Xingpeng Li
type: Java Code
zip: 
timeInit: 2023-09-13
time: 2023-09-13
github: https://github.com/rpglab/GRTOS
paper: 
link: 
doi: 
description: "This is a software suite for power grid real-time energy management system (EMS). It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules."
---


This is a software suite for power grid real-time energy management system (EMS). It consists of multiple modules: AC power flow, AC real-time contingency analysis (RTCA), AC transmission switching (TS), real-time security-constrained economic dispatch (RT-SCED), and interfacing of information flow between all these modules.


#### Papers from this GRTOS software:
With this software, we were able to publish multiple papers, some of which are provided below:

* Xingpeng Li, Pranavamoorthy Balasubramanian, Mostafa Sahraei-Ardakani, Mojdeh Abdi-Khorsand, Kory W. Hedman, and Robin Podmore, “Real-Time Contingency Analysis with Correct Transmission Switching,” *<u>IEEE Transactions on Power Systems</u>*, vol. 32, no. 4, pp. 2604-2617, Jul. 2017. <a class="" target="_blank" href="/papers/XLI-RTCAwCTS/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhanced Energy Management System with Corrective Transmission Switching Strategy— Part I: Methodology,” *<u>IEEE Transactions on Power Systems</u>*, vol. 34, no. 6, pp. 4490-4502, Nov. 2019. <a class="" target="_blank" href="/papers/XingpengLi-KWH-TPWRS-Part-I/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhanced Energy Management System with Corrective Transmission Switching Strategy— Part II: Results and Discussion,” *<u>IEEE Transactions on Power Systems</u>*, vol. 34, no. 6, pp. 4503-4513, Nov. 2019. <a class="" target="_blank" href="/papers/XingpengLi-KWH-TPWRS-Part-II/">[Link Here]</a>

* Xingpeng Li, Pranavamoorthy Balasubramanian, Mojdeh Abdi-Khorsand, Akshay S. Korad, and Kory W. Hedman, “Effect of Topology Control on System Reliability: TVA Test Case,” *CIGRE US National Committee Grid of the Future Symposium*, Houston, TX, USA, Oct. 2014. <a class="" target="_blank" href="/papers/XLi-ASU-Cigre/">[Link Here]</a>

* Pranavamoorthy Balasubramanian, Mostafa Sahraei-Ardakani, Xingpeng Li, and Kory W. Hedman, “Towards Smart Corrective Switching: Analysis and Advancement of PJM’s Switching Solutions,” *IET Generation, Transmission, and Distribution*, vol. 10, no. 8, pp. 1984-1992, May 2016. <a class="" target="_blank" href="/papers/Pranav-PJM_Switching_Soln/">[Link Here]</a>

* Mostafa Sahraei-Ardakani, Xingpeng Li, Pranavamoorthy Balasubramanian, Kory W. Hedman, and Mojdeh Abdi-Khorsand, “Real-Time Contingency Analysis with Transmission Switching on Real Power System Data,” *<u>IEEE Transactions on Power Systems</u>*, vol. 31, no. 3, pp. 2501-2502, May 2016. <a class="" target="_blank" href="/papers/RTCAwTS-ASU-Letter/">[Link Here]</a>

* Xingpeng Li, Pranavamoorthy Balasubramanian, and Kory W. Hedman, “A Data-driven Heuristic for Corrective Transmission Switching,” *North American Power Symposium (NAPS)*, Denver, CO, USA, Sep. 2016. <a class="" target="_blank" href="/papers/XLI-NAPS-DD-CTS/">[Link Here]</a>

* Xingpeng Li and Kory W. Hedman, “Enhancing Power System Cyber-Security with Systematic Two-Stage Detection Strategy,” *<u>IEEE Transactions on Power Systems</u>*, vol. 35, no. 2, pp. 1549-1561, Mar. 2020. <a class="" target="_blank" href="/papers/XLI-CyberSecurity/">[Link Here]</a>

* Xingpeng Li, “Fast Heuristic AC Power Flow Analysis with Data-Driven Enhanced Linearized Model,” *Energies*, 13(13), 3308, Jun. 2020. <a class="" target="_blank" href="/papers/XLI-DD-ACPF-Energies/">[Link Here]</a>

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
	* transmissionswitching: implements both sequential and parallel corrective TS, as well as relevant features: multiple methods for determining candidate switching list, best TS line (with/without pareto improvement) and violation relief recording.
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


#### Parallel Computing:
There are parallel computing versions for the following two applications: (i) contingency analysis and (ii) transmission swtiching.

The parallel computing package utilized here is MPJ Express: 
 * http://mpjexpress.org/

Instructions about how to set up MPJ Express in Eclipse: 
 * https://www.youtube.com/watch?v=ROXFfUbgY98

How to use MPJExpress:
1. Download MPJ Express and unpack it. 
2. Set MPJ_HOME and PATH environmental variables:
      * export MPJ_HOME=/path/to/mpj/
      * export PATH=$MPJ_HOME/bin:$PATH 
      * (These above two lines can be added to the end of ~/.bashrc)
3. Write your MPJ Express program (HelloWorld.java) and save it. 
4. Compile in cmd: 
	  * javac -cp .:$MPJ_HOME/lib/mpj.jar HelloWorld.java
	  * (or: javac -cp “.:$MPJ_HOME/lib/mpj.jar:/path/to/jar/file” HelloWorld.java)
	  * (or: javac -cp .:$MPJ_HOME/lib/mpj.jar:/path/to/jar/file HelloWorld.java)
5. Execute in cmd: 
	  * mpjrun.sh -np 4 HelloWorld
	  * (or: mpjrun.sh -np 4 -cp .:/path/to/jar/file HelloWorld)

If third-party package is used:
* Steps 1 - 3 remain the same; 	
* Step 4: javac -cp .:$MPJ_HOME/lib/mpj.jar testA/testB/MainClass.java testA/testB/DataProcessor.java     (MainClass.java and DataProcessor.java are both in folder testA/testB.)
* Step 5: mpjrun.sh –np 4 testA.testB.MainClass      (MainClass is in package testA.testB;)

If non-default java is preferred, add the following three lines on top of file mpjrun.sh:
* export MPJ_HOME=/usr/gapps/ppp/mpj/mpj-v0_43
* export JAVA_HOME=/path/to/the/non/default/java
* export PATH=$MPJ_HOME/bin:$JAVA_HOME/bin:$PATH

Of course, some “java” in this file have to be changed to /path/to/the/non/default/java)

When in the cluster mode, use the following commands:
* mpjrun.sh -np 2 native -dev niodev HelloWorld
* mpjrun.sh -np 2 -dev niodev HelloWorld
* mpjrun.sh -np 2 -dev niodev -jar $MPJ_HOME/lib/test.jar


#### Run commands:
Examples, when using Eclipse, use: run Configurations or debug Configurations; in the arguments box, enter: 
 * --uri psseraw:file=IEEE14busPsse30.raw&lowx=adjust --voltage flat 
 * or: --uri psseraw:path=cases/IEEE118busSystemData&lowx=adjust --voltage flat

On linux the arguments should be:
* --uri psseraw:file=IEEE118busPsse30.raw\&lowx=adjust --voltage flat -debug /tmp/ieeedbg -results results.csv
* (use \& instead of &)

When using cplex, the JVM argument should be: 
* -Djava.library.path=/path/to/cplex1251.dll
* e.g., -Djava.library.path=M:\_software\java\

Convert a psse.raw file to some files.csv using the following command:
* --dir tmp --psse IEEE300busPsse30.raw --version 30
* (Note: the folder tmp should be there before the program initialized, otherwise, it would fail.)


In Linux, here are some example commands:
1. Sample system environment variables set-up:
	* export MPJ_HOME=/home/xingpeng/mpj-v0_40
	* export PATH=$MPJ_HOME/bin:$PATH	
2. Sample compile command:
	* javac -cp .:$MPJ_HOME/lib/mpj.jar:/home/xingpeng/ExternalJar/junit-4.11.jar:/home/xingpeng/ExternalJar/cplex.jar com/utilxl/array/\*.java com/utilxl/iofiles/\*.java com/utilxl/string/\*.java com/powerdata/openpa/psse/\*.java com/rtca_cts/ausXP/\*.java com/rtca_cts/batch/\*.java com/rtca_cts/contingencyanalysis/\*.java 
	* (need to include all classes in each folder/subfolder, space in between is needed)
3. Sample execution command:
	* java -cp .:/home/xingpeng/ExternalJar/junit-4.11.jar com.rtca_cts.batch.BatchCorrectiveTransmSwitNaiveSeq
	* (select a specific application to execute)

Sample commands when using MPJ Express:
* mpjrun.sh -np 2 -cp .:/home/xingpeng/javaJar/junit-4.11.jar com.rtca_cts.contingencyanalysis.ContingencyAnalysisParallel --uri psseraw:file=IEEE14busPsse30.raw\&lowx=adjust --voltage flat
* mpjrun.sh -np 8 -cp .:/home/xingpeng/ExternalJar/junit-4.11.jar com.rtca_cts.batch.BatchCorrectiveTransmSwitNaiveParallel


#### Required external .jar files:
* MPJ Express
* gurobi
* junit


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

Three practical power systems (Tennessee Valley Authority (TVA), Electric Reliability Council of Texas (ERCOT), and PJM) were used to test some applications of this software suite. These system data are sensitive thus, are not shared here.


#### Input Files:
* input/*.raw: PSS/E raw file (version 29 or 30): power flow data for PF/RTCA/TS.
* input/sced_ver01/*: generator cost and ramping limit information.
* input/FDI_model/*: FDI simulation data for FDID evaluation.
* dataToRead/*: additional data files to read for some specific application programs.
* CpsConfg.ini: the configure file that the program will first read.


#### Output Files:
All output files will be generated in this folder 'filesOfOutput'. Log will be automatically generated and stored in the folder 'log'.


## Acknowledgment and Contributions:
This suite of software packages was initiated in 2014, and was developed and extended over the next few years until 2020. This software suite was developed around OpenPA (first version) that is an open-source AC power flow tool developed by PowerData Corpration, Incremental Systems Corporation. Their copyright note is included in each of the code file in the folder 'src/com/powerdata/'. Some modifications were made to best interface with other codes for RTCA, TS, and SCED.

Xingpeng Li was the main coder/developer with the support from the teammates (co-authors of the aforementioned papers) under the supervision of Prof. Kory W. Hedman at Arizona State University (ASU) in 2013 - 2017. At ASU, this work was supported by 1) the Department of Energy Advanced Research Projects Agency - Energy (ARPA-E), under the Green Electricity Network Integration program and under the Network Optimized Distributed Energy Systems program, and 2) the National Science Foundation (NSF) award (1449080). In 2018-2020, some further modifications were made and a few new classes were created by Xingpeng Li at the University of Houston. 


## Citation:
If you use any codes/data here for your work, please cite the relevant papers listed above as your references.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>

Note that the codes under folder 'src/com/powerdata/' were developed by PowerData Corpration, Incremental Systems Corporation. They are under a different license: BSD-3-Clause license; their copyright note is provided in each of the code file in this folder.


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

