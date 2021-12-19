---
layout: resource
title: Fast Decoupled Power Flow in Matlab
authors: Xingpeng Li
type: Matlab Code
zip: /zips/codes_matlab/FDPF.zip
timeInit: 2021-12-19
time: 2021-12-19
github: https://github.com/rpglab/FDPF
link: 
doi: 
description: This set of codes implements the Fast Decoupled AC Power Flow method.
---


# Fast Decoupled AC Power Flow (FDPF)
This is a set of Matlab codes that solves AC power flow problems using the Fast Decoupled method.

The main program is *main.m*. In this file, you can set multiple parameters including algorithm and starting point. In the file *initial.m*, you can set the power flow method parameters such as precision threshold and maximum number of iterations.

Some codes and comments in file FormYbus.m are (with some modifications) from Matpower user manual and makeYbus.m file. 

The test cases including a 3-bus system, 5-bus system, 24-bus system, 39-bus system, 118-bus system and a 2383-bus system. They are briefly explained below and also described with more details in the case files. 

Six test cases are included here for users' convenience. They are described below:

* 3-bus test system: the original data of this test case are from the following reference: <a class="off" href="/resources/ECE6379-PSOM/"  target="_blank">Li, Xingpeng (2021): ECE6379_PSOM.zip. figshare. Online resource. https://doi.org/10.6084/m9.figshare.17161805.v1</a>

* 5-bus test system: the original data of this test case are from the following reference: Xi-Fan Wang, Yonghua Song, and Malcolm Irving, "Modern Power Systems Analysis", Springer; 2009th edition (December 14, 2011). 

* IEEE 14-bus test system: this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the link below (in IEEE Common Data Format (ieee14cdf.txt)): https://labs.ece.uw.edu/pstca/pf14/ieee14cdf.txt

* IEEE 39-bus test case (New England system): this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the following reference: G. W. Bills, et.al., "On-Line Stability Analysis Study" RP90-1 Report for the Edison Electric Institute, October 12, 1970, pp. 1-20 - 1-35. prepared by E. M. Gulachenski with New England Electric System and J. M. Undrill with General Electric Co.

* IEEE 118-bus test system: this test case was converted from matpower (https://matpower.org/). The original data of this test case are from the link below (in IEEE Common Data Format (ieee118cdf.txt)): https://labs.ece.uw.edu/pstca/pf118/ieee118cdf.txt

* 2383-bus Polish system: this test case was converted from matpower (https://matpower.org/). The data was provided by Roman Korab (roman.korab@polsl.pl).

The power flow results are compared and verified with the results obtained from Matpower using Newton's method. For small test cases, it works very well. For the large-scale 2383-bus system, obvious mismatches between this program and Matpower are observed. Not sure what made the difference; possibly (i) the cases used by two tools are not entirely the same; (ii) difference between Newton's method and Fast Decoupled method; (iii) different control schemes; e.g., this program does not adjust transformer taps or shunts.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

