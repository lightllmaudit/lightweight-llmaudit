# Our Experiment

This repository contains the code and datasets for the experiments related to our multi-stage vulnerability management pipeline. The project is organized into four main components: **Vulnerability Detector**, **Vulnerability Explanator**, **Severity Determinants**, and **Recommender**.

## Directory Structure

The project is divided into four main directories, each corresponding to a core component of the pipeline:

* `detector/`: Experiments for smart contract vulnerability detection.
* `explanator/`: Experiments for generating natural language explanations of vulnerabilities.
* `severity/`: Experiments for classifying the severity of detected vulnerabilities.
* `recommender/`: Experiments for generating remediation recommendation for vulnerabilities.

Each component directory follows a similar internal structure:
* `dataset/`: Contains the training, validation, and test data splits.
* `ours/`: Contains the implementation of our proposed method.
* `baseline/` or `(finetuned/zeroshot)_baseline/`: Contains the implementations for various baseline models used for comparison.

## Detector

This component focuses on classification task to detect whether a smart contract is vulnerable.

* **`dataset/`**: Contains the smart contract datasets (`smart_contract_train.csv`, `smart_contract_val.csv`, `smart_contract_test.csv`).
* **`ours/`**: Implements our proposed detection model in `detector.ipynb`.
* **`finetuned_baseline/`**: Notebooks for fine-tuned baseline models like CodeBERT, GraphCodeBERT, CodeT5, UniXcoder, and CodeLlama.
* **`zeroshot_baseline/`**: Notebooks for zero-shot baseline models like CodeLlama (13B, 34B) and GPT models.


## Explanator

This component focuses on **generating natural language explanations** for vulnerabilities. Our approach involves multiple steps like CoT generation, candidate inference, and aggregation.

* **`dataset/`**: Contains the datasets for training and evaluating the explanator, including versions with Chain-of-Thought (CoT) reasoning (`vuln_data_*_with_CoT.csv`).
* **`ours/`**: Contains the multi-step implementation of our proposed explanator:
    * `Cot_Generation.ipynb`: The CoT Knowledge Distillation process
    * `Ours_VulnExp.ipynb`: Training process of our method
    * `Candidate_Inference.ipynb`: Candidate Inference of our method
    * `Aggregation_Inference.ipynb`: Aggreggation Inference of our method
* **`baseline/`**: Notebooks for fine-tuned and zero-shot baseline models.

## Severity

This component focuses on **classifying the severity** of a known vulnerability.

* **`dataset/`**: Contains the severity classification datasets (`severity_data_train.csv`, `severity_data_val.csv`, `severity_data_test.csv`).
* **`ours/`**: Implements our proposed severity classification model in `severity.ipynb`.
* **`finetuned_baseline/`**: Notebooks for fine-tuned baseline models.
* **`zeroshot_baseline/`**: Notebooks for zero-shot baseline models.

## Recommender

This component focuses on **generating remediation recommendation** to fix vulnerabilities. It follows a similar multi-step approach as the explanator.

* **`dataset/`**: Contains the datasets for the recommendation task, including versions with CoT reasoning (`vuln_data_*_with_recom_CoT.csv`).
* **`ours/`**: Contains the multi-step implementation of our proposed recommender:
    * `CoT_Recommendation_Generation.ipynb`: The CoT Knowledge Distillation process
    * `Ours_Recom.ipynb`: Training process of our method
    * `Recom_Candidate_Inference.ipynb`Candidate Inference of our method
    * `Recom_Aggregation_Inference.ipynb`: Aggreggation Inference of our method
* **`baseline/`**: Notebooks for fine-tuned and zero-shot baseline models.