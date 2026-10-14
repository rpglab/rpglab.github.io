---
layout: resource
title: ML-based ERCOT Net-Load Forecasting in Python Notebook
authors: Oluwafolajimi Samuel Bolusteve, Linhan Fang
type: Python Code
zip: 
timeInit: 2026-10-13
time: 2026-10-13
github: https://github.com/rpglab/ML_ERCOT-NetLoad_Forecasting
paper: /papers/Samuel-Linhan-NetLoad-forecast/
link: 
doi: 
description: "This is for our TPEC paper: *Net Load Forecasting with Renewable Capacity Features: A Comparison of Direct and Indirect Neural Network Methods*. It implements direct & indirect FCNN and LSTM models for ERCOT net-load forecasting."
---


This set of codes/data implements our TPEC paper "Net Load Forecasting with Renewable Capacity Features: A Comparison of Direct and Indirect Neural Network Methods".

This repository contains reproducible Jupyter Notebook implementations of four hourly ERCOT net-load forecasting pipelines:

1. FCNN direct forecasting;
2. FCNN indirect forecasting;
3. LSTM direct forecasting;
4. LSTM indirect forecasting.

The indirect methods predict total load, solar generation, and wind generation separately, then calculate:

```text
predicted net load
= predicted total load
- predicted solar generation
- predicted wind generation
```

All four methods forecast net load one hour ahead from a 24-hour input window, use installed wind and solar capacity as input features, and use a chronological 90%/5%/5% training/validation/test split. On the common test set, the indirect LSTM achieves the best overall accuracy (MAPE 2.46%, RMSPE 3.59%, and R² 98.7%).

Only the enhanced LSTM solar model is included and used by the LSTM indirect workflow.


## Repository structure

```text
Data Download/                 ERCOT 2021-2024 source workbooks and optional plots
Data Preparation/              Canonical timestamp-aligned data preparation
FCNN Direct Method/            FCNN direct model
FCNN Indirect Method/          FCNN component models and indirect result
LSTM Direct Method/            LSTM direct model and optional result plot
LSTM Indirect Method/          LSTM component models and indirect result
Results/                       Four-method comparison, Fig. 8/12 plotting, and Table IV APE statistics
fixed_data/                    Canonical model input in CSV/XLSX form
fixed_outputs/                 Final net-load predictions of the four methods
figures/                       Regenerated 600 dpi paper figures
requirements.txt               Tested Python dependencies
```

`fixed_outputs/` contains the final net-load prediction files of the four methods. Retraining a model writes its artifacts and regenerated predictions to the same directory.


## Environment

Python 3.9 is recommended because the notebooks were developed with TensorFlow 2.10.

```bash
python -m venv .venv
```

Activate the environment, then install the pinned dependencies:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m notebook
```

TensorFlow CPU is sufficient. GPU execution requires a TensorFlow-compatible CUDA/cuDNN installation and may produce small hardware-dependent numerical differences.


## Data

### Official ERCOT download source

The annual source workbooks were obtained from ERCOT's public **Hourly Aggregated Wind and Solar Output** data product:

- <a class="" href="https://www.ercot.com/gridinfo/generation/index.html" target="_blank">ERCOT Generation page</a> — open **Intermittent Renewable Resources**, then select **Hourly Aggregated Wind and Solar Output**;
- <a class="" href="https://www.ercot.com/mp/data-products/data-product-details?id=PG7-126-M" target="_blank">Hourly Aggregated Wind and Solar Output data-product page</a> — EMIL ID `PG7-126-M`, Report Type ID `13424`.

ERCOT exposes the available annual files dynamically, so direct year-specific download URLs may change. If that happens, use the data-product page above and select the required year from **Available Files**. These links were verified on August 29, 2026. The exact 2021-2024 workbooks used by this repository are also included in `Data Download/` for reproducibility.

### Canonical dataset

The ready-to-use canonical dataset is included:

- `fixed_data/ercot_2021_2024_hourly.csv` — model input;
- `fixed_data/ercot_2021_2024_hourly.xlsx` — human-readable copy;
- `fixed_data/ercot_2021_2024_audit.json` — row-count and integrity summary.

It contains 35,065 continuous hourly timestamps from `2021-01-01 06:00:00` through `2025-01-01 06:00:00`. Timestamps are timezone-naive UTC keys converted from the ERCOT `America/Chicago` clock, so the daylight-saving transition remains unique and continuous.

The model workflows can use the included canonical CSV directly. To regenerate it from the four included ERCOT Wind/Solar workbooks, run:

```text
Data Preparation/01_Prepare_Available_ERCOT_Data.ipynb
```

This preparation notebook reads:

```text
Data Download/ERCOT_2021_Hourly_WindSolar_Output.xlsx
Data Download/ERCOT_2022_Hourly_WindSolar_Output.xlsx
Data Download/ERCOT_2023_Hourly_WindSolar_Output.xlsx
Data Download/ERCOT_2024_Hourly_WindSolar_Output.xlsx
```

Running the preparation notebook rewrites the three files in `fixed_data/`. It validates timestamps, hourly continuity, missing values, nonnegative renewable generation/capacity, one-to-one wind/solar alignment, and the net-load identity.

The forecasting code does not require the legacy NLDAS files. Solar forecasting uses generation/capacity history, local calendar information, and `clear_sky_proxy`; wind forecasting uses generation/capacity history and local calendar information.


## Running order

The direct and indirect branches may be trained independently. Within each indirect branch, run the three component models before the result notebook.

### FCNN direct

```text
FCNN Direct Method/FCNN_net load.ipynb
```

### FCNN indirect

```text
FCNN Indirect Method/1_FCNN_total load.ipynb
FCNN Indirect Method/2_FCNN_solar power.ipynb
FCNN Indirect Method/3_FCNN_wind power.ipynb
FCNN Indirect Method/4_FCNN_indirect result.ipynb
```

### LSTM direct

```text
LSTM Direct Method/LSTM_net load.ipynb
LSTM Direct Method/LSTM Direct Prediction Graph.ipynb  # optional plot
```

### LSTM indirect

```text
LSTM Indirect Method/1_LSTM_total load.ipynb
LSTM Indirect Method/2_LSTM_wind power.ipynb
LSTM Indirect Method/3_LSTM_solar power.ipynb
LSTM Indirect Method/4_LSTM_indirect result.ipynb
```

### Comparison and paper figures

After all four final prediction files exist, run:

```text
Results/05_Compare_Four_Methods.ipynb
```

The comparison uses only timestamps shared by all four methods and verifies that their actual net-load targets agree before calculating metrics.

To regenerate the paper's percentage-error plots and Table IV statistics from the four final prediction files, run:

```text
Results/06_Plot_Percentage_Errors.ipynb
```

This notebook saves the percentage-error figures for Fig. 8 (FCNN) and Fig. 12 (LSTM), in both standard and enhanced signed-error/APE-ECDF versions, to `figures/` at 600 dpi. The LSTM direct notebook saves the Fig. 9 loss curve, the FCNN direct notebook saves an optional diagnostic loss curve, and the four method workflows save Fig. 6, Fig. 7, Fig. 10, and Fig. 11 to the same directory.


## Output contract

Every trained component writes uniquely named artifacts to `fixed_outputs/`:

- a TensorFlow `.keras` model;
- a preprocessing `.joblib` file;
- training history in CSV format;
- predictions in CSV and XLSX formats;
- metrics in JSON format.

Prediction tables use the common columns `time`, `actual`, and `predict`. Indirect result notebooks align all component files by timestamp with one-to-one merge validation rather than positional arithmetic.


## Reproducibility safeguards

- chronological train/validation/test splits;
- preprocessing fitted on training data only;
- sequence-window continuity checks;
- fixed Python, NumPy, and TensorFlow random seeds;
- deterministic TensorFlow operations where supported;
- `shuffle=False` during time-series training;
- nonnegative and installed-capacity constraints for renewable predictions;
- zero-safe percentage metrics;
- common-timestamp comparison across the four final methods.

Notebook outputs already stored in the files are retained as reference results. They are not required for execution; running the notebooks regenerates external artifacts in `fixed_outputs/`.


## Contributions:
Oluwafolajimi Samuel Bolusteve and Linhan Fang developed this set of programs/data. Xingpeng Li supervised this work.


## Citation:
If you use any of our codes/data for your work, please cite the following paper as your reference:

Oluwafolajimi Samuel Bolusteve, Linhan Fang, and Xingpeng Li, “Net Load Forecasting with Renewable Capacity Features: A Comparison of Direct and Indirect Neural Network Methods”, *IEEE Texas Power and Energy Conference*, College Station, TX, USA, Feb. 2027.

Paper website: <a class="off" href="/papers/Samuel-Linhan-NetLoad-forecast/"  target="_blank">https://rpglab.github.io/papers/Samuel-Linhan-NetLoad-forecast/</a>



## Contact:
Dr. Xingpeng Li

University of Houston

Email: xli83@central.uh.edu

Website: <a class="off" href="/"  target="_blank">https://rpglab.github.io/</a>


## License:
This work is licensed under the terms of the <a class="off" href="https://creativecommons.org/licenses/by/4.0/"  target="_blank">Creative Commons Attribution 4.0 (CC BY 4.0) license.</a>


## Disclaimer:
The author doesn’t make any warranty for the accuracy, completeness, or usefulness of any information disclosed; and the author assumes no liability or responsibility for any errors or omissions for the information (data/code/results etc) disclosed.

