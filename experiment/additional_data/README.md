# Analysis & Plotting

This directory contains the primary data, evaluation results, and plotting scripts presented in the paper.

## Overview

Most of the data supporting the paper's findings are located here. All plots were generated using the `Plotting_preparation.ipynb` notebook, which processes the raw data files in this folder. The final plots are available in the `_plot_result/` directory.

This folder specifically contains:
* The evaluation results for the **vulnerability explanator**.
* The evaluation results for the **recommender**.
* The extension analysis for the **vulnerability detector** and **severity** models.

## Detailed Classification Report

A more detailed **classification report** (to 4 decimal places) is also calculated within the `Plotting_preparation.ipynb` notebook. The calculations for metrics like precision, recall, and F1-score are based on the confusion matrix results located in the [performance_experiment/severity](../performance_experiment/severity/) and [performance_experiment/detector](../performance_experiment/detector/) directory.


## File Descriptions

* **`Plotting_preparation.ipynb`**: The main Jupyter Notebook used to process all raw data and generate the figures used in the paper.
* **`_plot_result/`**: This directory contains the final plots in `.pdf` format.
* **`*.csv` files**: These files contain the raw evaluation outputs for the explanator and recommendator components, testing various models like CodeLlama (fine-tuned and zero-shot) and GPT-4o.
* **`*.pkl` files**: These are pickled Python objects containing the ground truth labels (`y_test_*`) and model predictions (`y_preds_*`) for the vulnerability detection and severity determination tasks.