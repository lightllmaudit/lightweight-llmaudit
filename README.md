# Lightweight LLMs for Smart Contract Auditing via Task-Aware Fine-Tuning and Distillation

This repository contains all the code, data, and results for our paper for detecting, classifying, explaining, and remediating smart contract vulnerabilities using lightweight LLM.

## Checkpoint Models

Our fine-tuned models and the specific versions of the baseline models used in the paper are available for download. This allows for direct use in inference without re-training.

## Repository Structure

The project is organized into two main directories, reflecting the overall workflow from data preparation to experimentation.

  * **`data_preprocess/`**: Contains all scripts and intermediate files for cleaning, processing, and splitting the raw data into the final datasets used for training and evaluation.
  * **`experiment/`**: Contains the core code for all experiments, including model implementations, resource usage analysis, and final result plotting.

## `experiment/`

This directory contains all the experimental code and is subdivided into three parts: performance experiments, resource analysis, and result aggregation.

### `performance_experiment/`

This is the core directory for all model training and evaluation, structured into four components:

  * **`detector/`**: Experiments for vulnerability detection.
  * **`severity/`**: Experiments for severity classification.
  * **`explanator/`**: Experiments for generating vulnerability explanations.
  * **`recommender/`**: Experiments for generating code fixes.

Each component folder contains the **`dataset/`**, our proposed model in **`ours/`**, and baseline models in **`finetuned_baseline/`** and **`zeroshot_baseline/`**.

### `resource_usage_experiment/`

This directory is dedicated to analyzing the computational efficiency of the models.

  * **`Resource Usage.ipynb`**: The notebook for processing and plotting performance data.
  * **`_resource_data/`**: Contains raw logs (`.pkl` files) for **GPU memory usage** and **GPU utilization**

### `additional_data/`

This directory is for synthesizing the final results and figures for the paper.

  * **`Plotting_preparation.ipynb`**: The main notebook for generating final plots and tables.
  * **`_plot_result/`**: Contains the final, paper-ready figures in `.pdf` format.
  * **`*.csv` & `*.pkl`**: Raw prediction outputs and final evaluation scores.

## Getting Started

### Installation

To set up the necessary environment, install the required packages using `pip`:

```bash
pip install -r requirements.txt
```

### Reproducibility Workflow

To fully reproduce the results presented in the paper, please follow these steps in order:

1.  **Prepare the Data**: Navigate to `data_preprocess/` and run the notebooks sequentially to generate the final datasets.
2.  **Run Experiments**: Go to `experiment/performance_experiment/` and run the notebooks for our models and the baselines. This will generate the primary results and performance logs.
3.  **Analyze Resource Usage**: In `experiment/resource_usage_experiment/`, run the `Resource Usage.ipynb` notebook to analyze the logs generated in the previous step.
4.  **Generate Final Figures**: Finally, navigate to `experiment/additional_data/`. Ensure all necessary prediction and evaluation files from the previous steps are present, and then run `Plotting_preparation.ipynb` to create the paper's final figures and tables.