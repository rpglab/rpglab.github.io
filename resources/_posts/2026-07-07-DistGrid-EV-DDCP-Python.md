---
layout: resource
title: Optimal Planning for Distribution Grid with EV in Python Jupyter Notebook
authors: Linhan Fang
type: Python Code
zip: 
timeInit: 2026-07-07
time: 2026-07-07
github: https://github.com/rpglab/TIA_DistGrid-EV_DDCP
paper: /papers/Linhan-Elias-EV-Vios-Soln/
link: 
doi: 
description: "This is for our TIA paper: *Diagnosis-Driven Co-planning of Network Reinforcement and BESS for Distribution Grid with High Penetration of Electric Vehicles*. It implements proposed three-stage Diagnosis-Driven Co-Planning framework."
---

Optimal Planning for Distribution Grid with EV.

This set of codes/data implements our TIA paper "Diagnosis-Driven Co-planning of Network Reinforcement and BESS for Distribution Grid with High Penetration of Electric Vehicles". It implements the proposed three-stage Diagnosis-Driven Co-Planning (DDCP) framework for coordinated network reinforcement and BESS planning.


## Repository Summary:
This repository contains the five core Jupyter notebooks used in the TIA paper to evaluate EV-induced distribution grid stress and to test mitigation strategies based on line upgrades and battery energy storage systems (BESS). The workflow begins with EV-load impact analysis, identifies voltage and thermal violation thresholds, builds benchmark line-upgrade cases, solves the proposed DDCP planning model, and finally validates the BESS operation under the planned or upgraded network condition.

| File name | Roles and functions |
| 1_IAS_EV load impact_violation analysis.ipynb	|  EV impact and charger power sensitivity analysis 
| 2_IAS_Trigger_BESS.ipynb 			|  EV adoption trigger analysis 
| 3_IAS_Upgrade lines.ipynb 			|  EV impact assessment and line-upgrade benchmark 
| 4_IAS_DDCP.ipynb 				|  Proposed DDCP optimization model with BESS planning decisions 
| 5_IAS_BESS_operation.ipynb 			|  BESS operation and post-upgrade validation 


## Research Workflow
The five notebooks form a sequential research pipeline:

1. EV impact screening across system voltage levels
   The first notebook evaluates how EV charging demand affects feeder voltage and line loading under different voltage levels, EV adoption rates, and charging-power assumptions. It provides a broad screening of system stress before detailed planning models are applied.

2. EV adoption trigger identification 
   The second notebook identifies the EV penetration levels at which feeder constraints begin to fail. It generates trigger plots and heatmaps that summarize the onset of voltage violations, thermal overloads, and model collapse conditions.

3. Line upgrade benchmark construction 
   The third notebook evaluates direct physical capacity expansion by identifying overloaded branches and testing candidate line or cable upgrades. This benchmark is used to compare the proposed BESS-based DDCP solution against a conventional network upgrade strategy.

4. DDCP planning optimization  
   The fourth notebook implements the proposed DDCP model. It uses a DistFlow-based formulation with BESS placement, sizing, charging/discharging, SOC dynamics, voltage constraints, current constraints, and investment cost.

5. BESS operation and validation 
   The fifth notebook validates the planned solution by evaluating BESS operation and feeder performance after applying the selected planning or upgrade decisions. It reports voltage, current, BESS dispatch, and system-level operating results.


## Notebook Descriptions

### 1_IAS_EV_Load_Impact_Violation analysis.ipynb

This notebook performs a front-end EV impact analysis across multiple distribution voltage levels and EV charging power settings. It evaluates how feeder loading and bus voltage distributions change as EV adoption increases. It also generates summary figures for thermal stress, voltage stress, and system collapse behavior.

Main functions include:

- loading feeder active/reactive power data and EV-user information;
- adding EV charging demand to feeder buses;
- running DistFlow-based feeder simulations over EV adoption scenarios;
- comparing feeder stress across voltage levels such as 4.16 kV, 6.9 kV, and 13.8 kV;
- evaluating charger power sensitivity, including 5 kW, 10 kW, and 15 kW cases;
- generating line loading, voltage envelope, and collapse threshold figures.

Typical outputs include:

- `Result_Line_Loading_13.8_5.xlsx`
- `Result_Bus_Voltage_13.8_5.xlsx`
- `Bar_6.9kV_Collapse.png`
- `Line_6.9kV_Collapse_Fixed.png`
- `Final_Figure_*.png`
- `Envelope_Final_*.png`

### 2_IAS_Trigger_BESS.ipynb 

This notebook performs EV adoption trigger analysis. It sweeps EV penetration levels and evaluates when the feeder first experiences voltage-limit violations, current-limit violations, or infeasible/model-collapse conditions. It also generates publication-style figures summarizing violation thresholds and maximum loading conditions.

Main functions include:

- building EV-load scenarios from user-count and charging-power data;
- running DistFlow-based power flow optimization under different EV adoption rates;
- identifying EV penetration levels that trigger feeder violations;
- comparing the initial violation threshold with the maximum EV penetration that can still be mitigated by BESS;
- exporting line loading and bus voltage results for later visualization.

Typical outputs include:

- `EV_Adoption_Thresholds.png`
- `EV_Adoption_Thresholds_Colorblind_Friendly.png`
- `Loading_Heatmap.pdf`
- `Maximum_Loading_Heatmap.png`
- `Result_Line_Loading_13.8_5.xlsx`
- `Result_Bus_Voltage_13.8_5.xlsx`

### 3_IAS_Upgrade lines.ipynb 

This notebook evaluates the direct impact of EV charging on the feeder and implements the line upgrade benchmark. It loads feeder active/reactive power data, adds EV charging demand, builds the DistFlow model, and records voltage and current violations. It also includes helper functions for using real line lengths and selecting candidate upgrade lines.

Main functions include:

- loading feeder load data and network parameters;
- adding EV charging demand to selected buses;
- solving feeder operating conditions using a DistFlow optimization model;
- detecting overloaded branches and voltage violated buses;
- testing line or cable upgrade strategies using real line length information;
- exporting benchmark results for current, voltage, generation, BESS, and total system quantities.

Typical outputs include:

- `Result_Line_IAS.csv`
- `Result_Line_Overloads.csv`
- `I_ij_IAS_benchmark.csv`
- `V_i_IAS_benchmark.csv`
- `BESS_IAS_benchmark.csv`
- `P_ij_all.csv`
- `Q_ij_all.csv`
- `totals_all.csv`

### 4_IAS_DDCP.ipynb 

This notebook contains the main DDCP optimization model. It formulates the distribution planning problem with BESS placement and sizing decisions, feeder voltage constraints, branch flow constraints, current-related variables, and investment cost. The model is used to evaluate whether BESS-based planning can mitigate EV-induced voltage and thermal violations.

Main functions include:

- preparing load, EV, bus, branch, and voltage-reference data;
- constructing a DistFlow-based feeder optimization model in Gurobi;
- defining BESS energy capacity, charging/discharging power, SOC dynamics, and inverter-related limits;
- enforcing active/reactive power balance and voltage drop constraints;
- minimizing BESS investment-related cost and operating quantities;
- exporting detailed post-optimization reports for line currents, bus voltages, BESS dispatch, and system totals.

Typical outputs include:

- `Result_Line_IAS_13.8_DDCP.csv`
- `Result_Line_Overloads.csv`
- `I_ij_IAS.csv`
- `V_i_IAS.csv`
- `P_bess_IAS.csv`
- `Q_bess_IAS.csv`
- `BESS_IAS.csv`
- `totals_all.csv`

### 5_IAS_BESS_Operation.ipynb

This notebook focuses on BESS operation and validation after the planning or upgrade stage. It includes functions to update the feeder topology based on selected bottleneck lines, modify line limits and impedance values, and evaluate BESS dispatch under the revised network condition.

Main functions include:

- loading electricity price data and line length data;
- identifying topological bottleneck lines from diagnostic overload results;
- upgrading selected lines or protection devices using predefined equipment data;
- updating line limits and branch impedance parameters;
- fixing or extracting BESS planning results for operation-stage validation;
- exporting BESS operation, bus voltage, line current, and total system results.

Typical outputs include:

- `Result_Line_IAS_6.9_DDCP.csv`
- `I_ij_IAS_BESS.csv`
- `V_i_IAS_BESS.csv`
- `P_bess_IAS.csv`
- `Q_bess_IAS.csv`
- `BESS_IAS.csv`
- `totals_all.csv`


## Recommended Running Order

The notebooks are intended to be executed in the following order:

1_IAS_EV load impact_violation analysis.ipynb
 -> Screen EV-induced stress across voltage levels and EV charger power cases.

2_IAS_Trigger_BESS.ipynb 
 -> Identify EV adoption thresholds and violation patterns.

3_IAS_Upgrade lines.ipynb 
 -> Evaluate EV impact and line upgrade benchmark cases.

4_IAS_DDCP.ipynb 
 -> Solve the main DDCP planning model with BESS decisions.

5_IAS_BESS_Operation.ipynb
 -> Validate BESS operation and upgraded network performance.


## Required Input Data
The notebooks assume that the following input files are available in the working directory or that the file paths are updated accordingly:

- `Calculated Nodal P&Q.xlsx`  
  Feeder active and reactive load data.

- `users number_1120.xlsx`  
  User and EV-count information used to generate EV adoption scenarios.

- `bus1_voltage_mean.xlsx`  
  Slack-bus or reference-voltage time-series data.

- `length.xlsx`  
  Line length information used for cable upgrade cost, impedance updates, and physical line upgrade calculations.

- `houston_hourly_avg_price.xlsx`  
  Electricity price data used in the BESS operation and validation notebook.

The current notebooks contain local Windows paths in some data-loading cells. These paths should be replaced with relative paths before running the code on another machine.


## Software Requirements
The notebooks require the following Python packages:

	python >= 3.9
	
	numpy
	
	pandas
	
	matplotlib
	
	seaborn
	
	gurobipy
	
	opendssdirect.py
	
	openpyxl
	
	A valid Gurobi license is required to solve the optimization models.


## Citation:
If you use any of our codes/data for your work, please cite the following papers as your reference:

Linhan Fang, Elias Raffoul, and Xingpeng Li, “Diagnosis-Driven Co-planning of Network Reinforcement and BESS for Distribution Grid with High Penetration of Electric Vehicles”, *IEEE Transactions on Industry Applications*, Jun. 2026.

Paper website: <a class="off" href="/papers/Linhan-Elias-EV-Vios-Soln/"  target="_blank">https://rpglab.github.io/papers/Linhan-Elias-EV-Vios-Soln/</a>


## Contributions:
Linhan Fang developed this set of programs/data and implemented the proposed DDCP framework. Elias Raffoul analyzed EV counts for each bus and conducted the initial EV grid impact analysis. Xingpeng Li supervised this work.


## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: https://rpglab.github.io/


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.