# Zero-Shot Text Classification with Large Language Models (LLMs)

## I. Project Summary

This project documents the reproduction and demonstration of **Zero-Shot Text Classification (ZSL)** using a Large Language Model (LLM). The core objective is to classify text—specifically, tweets from the **COVID-19 Tweets Dataset**—into predefined sentiment categories (**Positive, Negative, Neutral**) without requiring any task-specific, labeled training data.

This implementation confirms the principles of zero-shot capability in LLMs, as detailed in contemporary research on the subject.

## II. Experiment Details

### A. Aim
To utilize a pre-trained Large Language Model (BART, specifically `facebook/bart-large-mnli`) to perform zero-shot text classification on the COVID-19 Tweets dataset and evaluate its performance against ground-truth data where applicable.

### B. Resources and Tools

| Category | Component | Details |
| :--- | :--- | :--- |
| **Programming Language** | Python | Executed via Jupyter Notebook or Google Colab. |
| **Key Libraries** | Python Ecosystem | `transformers`, `torch`, `pandas`, `numpy`, `matplotlib`. |
| **LLM Model** | BART (MNLI) | `facebook/bart-large-mnli` (Used for its capability in Natural Language Inference (NLI), which underpins ZSL). |
| **Dataset** | Primary Source | [COVID-19 Tweets Dataset (Kaggle)](https://www.kaggle.com/datasets/gpreda/all-covid19-vaccines-tweets) |
| **Hardware** | Execution Environment | GPU-enabled system (optional, but recommended for efficiency). |

## III. Methodology and Implementation

The methodology employs the **Zero-Shot Learning (ZSL)** paradigm, bypassing the need for traditional supervised training.

### A. Conceptual Basis: Zero-Shot Learning
ZSL relies on the LLM's vast general knowledge, acquired during pre-training, to infer the relationship between a piece of text and a set of candidate labels provided via a natural language prompt. The model does not see labeled examples of the specific task (e.g., COVID-19 sentiment) during deployment.

### B. Implementation Flow
1.  **Data Collection:** The tweets dataset is imported.
2.  **Preprocessing:** Minimal cleaning is applied (removal of URLs, hashtags) as LLMs handle most tokenization and stopword removal internally.
3.  **Classification:** The model is presented with a tweet and the candidate labels (`['positive', 'negative', 'neutral']`).
4.  **Scoring and Prediction:** The model computes the probability that the text belongs to each candidate label. The label with the highest confidence score is selected as the prediction.
5.  **Evaluation:** Standard classification metrics (**Accuracy, Precision, Recall, and $F_1$-score**) are calculated to quantify the model's zero-shot performance.

### C. Strategic Advantages
This LLM-based zero-shot approach offers several practical benefits for rapid prototyping and deployment:
* **Reduced Labor:** Eliminates the necessity of time-consuming manual data labeling.
* **High Adaptability:** The solution is immediately applicable to new text classification domains (e.g., spam detection, product review analysis) by simply modifying the candidate labels.
* **Robustness:** Demonstrates effective handling of unstructured and noisy data, such as social media text.

## IV. Repository Structure :
─ code1.py  # The core notebook containing the code implementation, output, and visualization.
-code2.py 
├── README.md              # Project documentation file (This document).
