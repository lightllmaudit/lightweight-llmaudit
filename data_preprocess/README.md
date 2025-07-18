# Vulnerability Extraction and Dataset Preparation Pipeline

This repository contains a pipeline for extracting, preprocessing, and cleaning vulnerability data for smart contracts, primarily sourced from Web3Bugs and further processed using large language models (LLMs). The end result is a clean, well-structured dataset for vulnerability detection tasks.

---

## Directory Structure

```
.
├── extract_vuln.ipynb       # Extract vulnerabilities from Web3Bugs dataset
├── preprocess_gpt.ipynb     # Preprocess data and prepare GPT input batches
├── cleaning.ipynb           # Clean and refine GPT outputs
├── vuln_only_extract.ipynb  # Filter and extract only vulnerability-related data
├── data_splitting.ipynb     # Split final dataset into training, validation, testing sets
├── final_dataset.csv        # Agregated dataset
├── vuln_dataset.csv         # Extracted vulnerability-only dataset
├── vuln_gpt.csv             # Intermediate dataset from GPT outputs
├── vulnerabilities.csv      # Raw extracted vulnerabilities
├── vulnerable_code.csv      # Vulnerable data
├── non_vulnerable_code.csv  # Raw non-vulnerable data
├── final_non_vuln_code.csv  # Sampled non-vulnerable data
└── README.md                # This file
```

---

## Workflow Overview

### **Extract Vulnerabilities**

* **Notebook**: `extract_vuln.ipynb`
* Extract vulnerability data from the **Web3Bugs dataset** and store it as raw data for further processing.
* Output: `vulnerabilities.csv`

---

### **Preprocess Data for GPT** and **LLM Extraction**

* **Notebook**: `preprocess_gpt.ipynb`
* Prepares data batches for LLM-based extraction and labeling.
* Generates `batch_inputs/` containing `batch_input_*.jsonl` files for LLM queries.

* Send the prepared inputs (`batch_inputs/`) to the LLM (e.g., GPT).
* Store the raw LLM responses in `batch_outputs/` as `batch_output_*.jsonl`.
* Output: `vuln_gpt.csv`,

---

### **Clean and Refine LLM Outputs**

* **Notebook**: `cleaning.ipynb`
* Processes raw LLM outputs, removing noise and consolidating extracted vulnerability information.
* Output: `vulnerable_code.csv`, `non_vulnerable_code.csv`, `final_non_vuln_code.csv`

---

### **Extract Vulnerability-Only Data**

* **Notebook**: `vuln_only_extract.ipynb`
* Filters out non-vulnerable data to create a vulnerability-only dataset.
* Output: `vuln_dataset.csv`

---

###  **Split Final Dataset**

* **Notebook**: `data_splitting.ipynb`
* Splits the final dataset into training, validation, and testing sets for all tasks.

---

## Folder Contents

| Folder           | Description                              |
| ---------------- | ---------------------------------------- |
| `batch_inputs/`  | JSONL files sent as LLM input batches.   |
| `batch_outputs/` | Raw JSONL responses returned by the LLM. |

---

## Final Outputs

| File                      | Description                                        |
| ------------------------- | -------------------------------------------------- |
| `final_dataset.csv`       | Aggregated dataset (vuln+non_vuln)            |
| `vuln_dataset.csv`        | Vulnerability-only dataset (that will be used to train and eval explanator, severity and recommender)                         |
| `final_non_vuln_code.csv` | clean non-vulnerable data (sampled so it will like the vuln samples)                  |
| `vulnerable_code.csv`     | vulnerable code data     |
| `non_vulnerable_code.csv` | raw non-vulnerable code (with test-related code and unsampled) |
