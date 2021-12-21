---
layout: resource
title: DCOPF in AMPL
authors: Xingpeng Li
type: AMPL Code
zip: /zips/ampl_codes/DCOPF-AMPL.zip
timeInit: 2021-12-09
time: 2021-12-09
github: https://github.com/rpglab/DCOPF
link: 
doi: 
description: This set of codes implements a normal lossless DCOPF model and two lossy DCOPF model.
---


## DCOPF
DC Optimal Power Flow (DCOPF): (i) one lossless DCOPF model and (ii) two lossy DCOPF models. The two lossy DCOPF models are explained as follows,

* Model 1 (M1) for lossy DCOPF: this model consists of (2)-(14) of the following paper: O. W. Akinbode and K. W. Hedman "Fictitious losses in the DCOPF with a piecewise linear approximation of losses," *IEEE PES General Meeting*, Jul. 2013.

* Model 2 (M2) for lossy DCOPF: this model is an iterative Loss approximation based model. For each iteration: it calculates total losses and then the change in losses than previous iteration; and then assign the losses to all/selected buses with same/different participation factors. This method converges when the difference of total losses between two consecutive iterations is less than a threshold. Possibly, two iterations repeat themselves, which cause this method NOT to converge.

Simulations: 
* The test case used here is a modified IEEE RTS-96 reliability test system (73-bus). The reference is: "The IEEE Reliability Test System-1996. A report prepared by the Reliability Test System Task Force of the Application of Probability Methods Subcommittee" and link is <a class="" target="_blank" href="https://ieeexplore.ieee.org/document/780914">here</a>. 

* Though only tested on this single system here, these codes can work on any other systems.

The following paper provides more details about Representation of Transmission Losses (how to assign losses to buses): 

* <a class="off" href="https://ieeexplore.ieee.org/document/8736407" target="_blank">Xingpeng Li and Kory W. Hedman, “Enhanced Energy Management System with Corrective Transmission Switching Strategy— Part I: Methodology,” IEEE Transactions on Power Systems, vol. 34, no. 6, pp. 4490-4502, Nov. 2019. (DOI: 10.1109/TPWRS.2019.2922880)</a>


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.