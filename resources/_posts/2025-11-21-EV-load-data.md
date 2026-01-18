---
layout: resource
title:  Multi-Year Residential Level-2 EV Charging Load Dataset at One-Hour Resolution
authors: Linhan Fang, Jesus Silva-Rodriguez.
type: Dataset
zip: 
timeInit: 2025-11-21
time: 2025-11-21
github: 
paper: /papers/Linhan-JesusS_EV-Datasets/
link: https://figshare.com/ndownloader/articles/30601655/versions/4
doi: 10.6084/m9.figshare.30601655
description: "This is for our arXiv paper: *Data-Driven EV Charging Load Profile Estimation and Typical EV Daily Load Dataset Generation*. This dataset includes EV starting/ending charge times, duration, and energy drawn from charging events."
---

(if the download/Figshare link shows '403' error, please use a different browser or the Chrome Incognito mode)


This dataset includes two sets of real-utility-data-derived synthetic multi-year residential level-2 EV charging load data, since two different/independent methods were developed to analyze the real utility data and generate this dataset.

This dataset can be used for both short-term operation studies and long-term planning studies.

This dataset was developed for distribution system studies, but it could also be leveraged to support transmission system studies.
 

### EV Data Description:
* The datasets include daily estimates for EV starting and ending charge times, duration, and energy drawn from charging event, 
* The datasets were statistically generated from data-driven analyses of real-world residential load data for customers with and without EV chargers registered. 
* The load profile estimations, as well as the overall projected EV charging behaviors for residential customers, were validated by comparison with other sources for real-world EV charging data directly obtained from EV charging stations.
* The datasets are meant to serve as synthetic EV charging data that can be used for distribution systems planning for areas with high projected EV penetration, as well as for power system operations and economic dispatch considering additional EV charging load data.


### Data Generation Methods:
* Two independent methods were implemented to analyze real utility data to generate two groups of EV charging load data respectively. The details can be found in the paper below.
* <a class="off" href="/people/Jesus-SilvaRodriguez/"  target="_blank">Jesus Silva-Rodriguez</a> implemented the STATISTICAL AGGREGATE CONSTANT LOAD METHOD.
* <a class="off" href="/people/Linhan-Fang/"  target="_blank">Linhan Fang</a> implemented the NORMALIZED SUBTRACTION METHOD.


### Data Loading Methods:
* Both Python codes and MATLAB codes that read/load the shared data are also provided.


## Citation:
If you use this dataset and/or the attached sample codes in your work, please cite the following paper. 

Linhan Fang, Jesus Silva-Rodriguez, and Xingpeng Li, “Data-Driven EV Charging Load Profile Estimation and Typical EV Daily Load Dataset Generation”, arXiv, Nov. 2025.


Paper website: <a class="off" href="/papers/Linhan-JesusS_EV-Datasets/"  target="_blank">https://rpglab.github.io/papers/Linhan-JesusS_EV-Datasets/</a>


## Contributions:
Linhan Fang and Jesus Silva-Rodriguez contributed equally to this work. Xingpeng Li supervised this work. 


## Contact:
If you need any techinical support, please feel free to reach out to <a class="" href="/people/Jesus-SilvaRodriguez/" target="_blank">Jesus Silva-Rodriguez</a> and/or <a class="" href="/people/Linhan-Fang/" target="_blank">Linhan Fang</a>.

For collaboration, please contact <a class="" href="/people/Xingpeng-Li/" target="_blank">Dr. Xingpeng Li</a> at xli83@central.uh.edu.

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.
