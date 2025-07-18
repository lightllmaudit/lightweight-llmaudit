# Resource Usage Analysis

This directory contains the data and code for analyzing the computational resource usage of the various models evaluated in our study.

## Overview

The primary goal here is to measure and compare the performance of our proposed models against baselines in terms of:
* **GPU Memory Usage**
* **GPU Utilization**

All the data processing and plot generation are handled by the `Resource Usage.ipynb` notebook.

## File Descriptions

### Notebook
* **`Resource Usage.ipynb`**: This is the main Jupyter Notebook. It loads the raw data from the `_resource_data/` directory, processes it, and generates the final plots and tables for our resource consumption analysis.

### Performance Data (`_resource_data/`)
This directory contains all the raw performance data collected during the experiments, saved as Python pickle files (`.pkl`).

The filenames follow a systematic naming convention: `[metric]_[model_identifier].pkl`.

* **`[metric]`** indicates the type of data recorded:
    * **`gpu_mem_`**: Peak GPU memory consumption.
    * **`gpu_utils_`**: GPU utilization percentage recorded over time.

* **`[model_identifier]`** specifies the model and task:
    * **`ours_*`**: Refers to our proposed models (e.g., `ours_detector`, `ours_severity`).
    * **`exp_*`**, **`rec_*`**, **`sev_*`**: Designate the Explanator, Recommender, and Severity tasks, respectively.
    * Other names like `codebert`, `ftcodellama13b`, or `zs_codellama34b` refer to the specific baseline models being evaluated.