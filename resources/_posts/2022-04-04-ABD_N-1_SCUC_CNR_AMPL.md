---
layout: resource
title: Accelerated-Decomposition Method for N-1 SCUC w. CNR in AMPL
authors: Arun Venkatesh Ramesh
type: AMPL Code
zip: /zips/ampl_codes/ABD_SCUCwCNR.zip
timeInit: 2022-04-04
time: 2022-04-04
github: https://github.com/rpglab/ABD-Alg_N-1_SCUC_CNR
link: 
doi: 
description: This set of codes implement various SCUC models with/without correct network reconfiguration (with/without decomposition).
---


## Day-Ahead N-1 Security-Constrained Unit-Commitment (SCUC) MILP models
This is a set of AMPL codes that perform day-ahead (24 Hours) unit-commitment which determines the generator dispatch and scheduling while considering N-1 reliability through post-contingency constraints for transmission contingencies. Authors have uploaded a few variations of the codes, namely, Extensive, Typical Benders-decomposition, and Accelerated Benders-decomposition approach. Another classification is the consideration of network flexibility through network reconfiguration as a corrective action implemented in post-contingency constraints. 
Note: For a detailed explanation of the model, please refer to the paper cited below.

AMPL program requires a data file (.dat), model file (.mod) and a run file (.run) to execute. The following summarizes the files in this codeset.

### Data files:
Data file contains transmission, generator, bus information along with a sample load profile and line-outage distribution factors of the respective network.
1. *dataFile24BusAll.dat* - Contains all basic parameters required for IEEE 24-bus system. 
2. *dataFile73BusAll.dat* - Contains all basic parameters required for IEEE 73-bus system.
3. *dataFilePolishAll.dat* - Contains all basic parameters required for Polish system with 2383 buses.

* IEEE 24-bus system is one of the three areas of the IEEE 73-bus system. They are described in this reference: "The IEEE Reliability Test System-1996. A report prepared by the Reliability Test System Task Force of the Application of Probability Methods Subcommittee" and link is <a class="" target="_blank" href="https://ieeexplore.ieee.org/document/780914">here</a>. 
* The 2383-bus Polish system was converted from matpower (https://matpower.org/). The data was provided by Roman Korab (roman.korab@polsl.pl).
* Some modifications may be made to the original data for the above systems.

### Model Files:
Model files defines the variables, parameters and mathematical constraints.
1. *Scuc_OriginalFormulation.mod* - Defines all constraints required for extensive model of N-1 SCUC constraints. 
2. *Scuc_OriginalFormulationWithCNRConstraints.mod* - Defines all constraints required for extensive model of N-1 SCUC with Corrective Network Reconfiguration (CNR) constraints.
3. *Scuc_BendersDecompositionConstraintsWithCNR.mod* - Defines all constraints required for benders decomposition based N-1 SCUC model with or without CNR. 

### Run Files:
Run file is script file that sequentially runs ampl commands. The main goal of the run file is to choose the appropriate datafile, select the solver (gurobi/cplex linear solvers for MILP/LP), define the constrains required for respective MILP/LP problems and solve the models. 
1. *ESCUC.run* - Extensive formulation of N-1 SCUC model.
2. *TSCUC.run* - Iterative Benders Decomposition based N-1 SCUC algorithm.
3. *ASCUC.run* - Iterative Accelerated Benders Decomposition based N-1 SCUC algorithm.
4. *ESCUCCNR.run* - Extensive formulation of N-1 SCUC considering Corrective Network Reconfiguration model.
5. *TSCUCCNR.run* - Iterative Benders Decomposition based N-1 SCUC with Corrective Network Reconfiguration algorithm.
6. *ASCUCCNR.run* - Iterative Accelerated Benders Decomposition based N-1 SCUC with Corrective Network Reconfiguration algorithm.

Note: The combination of data, model and run file are required to execute the above scripts. Decomposed models are iterative in nature whereas the extensive model is a single MILP problem which is co-optimized. Ensure that all files are in the same folder.

### How to execute:

1. Open AMPL IDE
2. Select folder with the above files
3. Open appropriate run file and un-comment the datafile (dataFile24BusAll.dat/dataFile73BusAll.dat/dataFilePolishAll.dat) required for execution.
4. In AMPL execute the command: include runFileName.run (for e.g. include ESCUC.run) 

Note: Extensive models require substantial computer resources to solve. Unrealistic for IEEE 73-bus system and polish network for ESCUCCNR, and polish network for ESCUC. Requires AMPL to be installed. Available Online: ampl.com


## Citation:
If you use these codes for your work, please cite the following paper:

<a class="off" href="/papers/ArunRamesh-AccDecompSCUC_CNR/" target="_blank">Arun Venkatesh Ramesh, Xingpeng Li and Kory W. Hedman, "An Accelerated-Decomposition Approach for Security-Constrained Unit Commitment With Corrective Network Reconfiguration," *IEEE Transactions on Power Systems*, vol. 37, no. 2, pp. 887-900, Mar. 2022. doi: 10.1109/TPWRS.2021.3098771.</a>

Paper website: <a class="off" href="/papers/ArunRamesh-AccDecompSCUC_CNR/"  target="_blank">https://rpglab.github.io/papers/ArunRamesh-AccDecompSCUC_CNR/</a>


## Contributions:
Built upon our existing <a class="" href="/resources/N-1_SCUC-AMPL/"  target="_blank">code</a>, Arun Venkatesh Ramesh developed this set of programs. Xingpeng Li provided the initial idea and supervised this work.


## Contact:
If you need any techinical support, please feel free to reach out to Arun Ramesh at aramesh4@uh.edu.

For collaboration, please contact Dr. Xingpeng Li at xli83@central.uh.edu.

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The authors don’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

