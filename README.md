# AI Fairness and A/B Testing Framework for Loan Risk Modeling

A specialized data science framework designed to rigorously compare competing loan approval models based on predictive accuracy, statistical significance, and critical AI fairness metrics.

---

## Project Title & Short Description

**Title:** AI Fairness and A/B Testing Framework for Loan Risk Modeling

**Description:** This project implements an A/B test simulation to compare a **Standard Loan Approval Model (A)** against a **Bias-Mitigated Model (B)**. The core focus is on quantifying model performance (Accuracy, F1 Score) and algorithmic fairness using the **Disparate Impact** metric.

---

## Problem Statement / Goal

The primary goal is to develop a production-ready loan risk assessment system that adheres to both high performance standards and critical **Ethical AI / fairness guidelines**. Specifically, the system aims to:
1.  Validate if a bias-mitigated modeling approach (Model B) offers statistically significant performance or fairness gains over the standard approach (Model A).
2.  Measure **Disparate Impact** to ensure the model does not disproportionately discriminate against protected groups in its lending decisions.

---

## Tech Stack / Tools Used

The project is implemented in Python and utilizes essential libraries for data handling, statistical modeling, and reporting:

| Category | Tool / Library | Purpose |
| :--- | :--- | :--- |
| **Data Handling** | Pandas | Data loading cleaning and manipulation |
| **Modeling** | Scikit-learn (Implied) | Core machine learning models and metrics (Accuracy F1 Score) |
| **Numerics** | NumPy (Implied) | Array operations and statistical calculations |
| **Reporting** | Pandas CSV | Generating a structured production report for stakeholders |

---

## Approach / Methodology

1.  **Data Preprocessing**: Loaded the loan data, performed essential data cleaning (e.g., string stripping), and split the data into training and testing sets.
2.  **Model Training**: Two distinct models—Model A (Standard) and Model B (Bias-Mitigated)—were trained for binary classification of `loan_status`.
3.  **Performance Evaluation**: Calculated standard metrics: **Accuracy** and **F1 Score** via cross-validation and on the final test set.
4.  **Fairness Assessment**: Calculated the **Disparate Impact (DI)** for both models (DI close to 1.0 indicates lower bias).
5.  **A/B Test Validation**: A statistical test (implied Chi-square test) was conducted to determine if the difference in **Approval Rate** between Model A and Model B was statistically significant.
6.  **Reporting**: A final production report was compiled and saved to CSV, summarizing all key metrics for business review.

---

## Results / Key Findings

The comparison between the two models yielded the following results on the test set:

| Model | Accuracy | F1 Score | Disparate Impact (Ideal = 1.0) | Approval Rate | Statistical Significance |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Standard (A)** | 0.9792 | 0.9833 | 1.0152 | 62.80% | - |
| **Bias-Mitigated (B)** | **0.9806** | **0.9845** | **1.0111** | **62.94%** | p=0.208 (NS) |

* **Performance**: Model B achieved marginally higher accuracy and F1 scores.
* **Fairness**: Model B demonstrated a slightly fairer outcome with a **Disparate Impact of 1.0111**, moving closer to parity than Model A (1.0152).
* **Conclusion**: The observed differences in performance and approval rate between Model A and Model B were **Not Statistically Significant (p=0.208)**, suggesting that the complexity of Model B does not yet justify its deployment over Model A based on these metrics alone.

---

## Topic Tags

A-BTesting AIFairness EthicalAI LoanRiskModeling FinancialServices MachineLearning BinaryClassification Python Pandas

---

## How to Run the Project

### 1. Install Requirements

Install all necessary packages using the provided `requirements.txt` file:

```bash
pip install -r requirements.txt
