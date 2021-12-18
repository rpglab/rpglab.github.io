---
layout: resource
title: PSS/E Raw File Loader in Java
authors: Xingpeng Li
type: Java Code
zip: /zips/ampl_codes/PSSE-Raw-File_Loader.zip
timeInit: 2021-12-13
time: 2021-12-13
github: https://github.com/rpglab/PSSE-Raw-File_Loader
link: 
doi: 
description: "This set of codes is used to read PSS/E raw files. So far, it can handle versions 32 and 33."
---


# PSSE-Raw-File Loader
This is a set of Java codes that load PSS/E raw files. So far, it can handle versions 32 and 33. Note that version number must be manually specified to ensure data are correctly loaded. Default values will be used when some data are not available. IDs, Names may contain blank space.

The main program/file is *PsseRawModel.java* in the package 'psseraw'.

For the path-to-raw-file, you can use relative path if in the folder with the codes, or use absolute path.

Note that this program reads all the data in the raw file except for multi-terminal DC transmission Lines, GNE devices, and Induction Machines. All loaded data are stored in the instance of PsseRawModel.java.

It takes less than 1 second to load all the data even for a large-scale system.

Three test cases are also uploaded here for users' convenience. They are described below:

IEEE 14-bus test system: the original data of this test case are from the link below (in IEEE Common Data Format (ieee14cdf.txt)): https://labs.ece.uw.edu/pstca/pf14/ieee14cdf.txt

IEEE 118-bus test system: The original data of this test case are from the link below (in IEEE Common Data Format (ieee118cdf.txt)): https://labs.ece.uw.edu/pstca/pf118/ieee118cdf.txt

2383-bus Polish system: This test case was converted from matpower (https://matpower.org/). The data was provided by Roman Korab (roman.korab@polsl.pl).


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

