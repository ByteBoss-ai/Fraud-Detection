# Credit Card Fraud Detection

## Overview
This project focuses on detecting fraudulent credit card transactions using machine learning. We evaluate **Decision Tree**, **Random Forest**, and **Logistic Regression** models on three different datasets:

1. **Original Dataset** – The raw dataset.
2. **Downsampled Dataset** – Balanced by downsampling normal transactions.
3. **SMOTE Oversampled Dataset** – Balanced using SMOTE (Synthetic Minority Oversampling Technique).

The goal is to accurately classify transactions as **Normal (0)** or **Fraud (1)**.

---

## Dataset
- **Source:** [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  
- **Features:** 30 anonymized numerical features (`V1`–`V28`, `Time`, `Amount`) and a target class `Class` (0 = Normal, 1 = Fraud)  
- **Missing Values:** None

---

## Approach

### 1. Data Exploration
- Checked dataset shape, head, tail, and descriptive statistics.
- Verified that there were no missing values.
- Plotted correlation heatmap and feature correlation with target to understand relationships.

### 2. Data Preprocessing
- Scaled `Time` and `Amount` features using `StandardScaler`.
- Created **downsampled** and **SMOTE oversampled** datasets to address class imbalance.

### 3. Feature-Target Split
- Split features (`X`) and target (`y`) for all datasets.
- Split datasets into training and testing sets (`80:20`).

### 4. Model Selection
- Evaluated three models:
  - Decision Tree Classifier
  - Random Forest Classifier
  - Logistic Regression

### 5. Evaluation Metrics
- **Accuracy:** Overall correctness  
- **Precision:** Correctly predicted fraud out of all predicted fraud  
- **Recall:** Correctly predicted fraud out of all actual fraud  
- **F1 Score:** Harmonic mean of precision and recall  
- **Confusion Matrix:** Visual representation of correct and incorrect predictions

---

## Model Performance
### Results Table

| Model | Sampling Method | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|---|
| Decision Tree | Original | 0.9990 | 0.6633 | 0.7222 | 0.6915 |
| Decision Tree | Downsampled | 0.9105 | 0.9381 | 0.8922 | 0.9146 |
| Decision Tree | SMOTE Oversampled | 0.9983 | 0.9976 | 0.9990 | 0.9983 |
| Logistic Regression | Original | 0.9992 | 0.8947 | 0.5667 | 0.6939 |
| Logistic Regression | Downsampled | 0.9316 | 0.9588 | 0.9118 | 0.9347 |
| Logistic Regression | SMOTE Oversampled | 0.9457 | 0.9727 | 0.9175 | 0.9443 |
| Random Forest | Original | 0.9995 | 0.9697 | 0.7111 | 0.8205 |
| Random Forest | Downsampled | 0.9368 | 0.9891 | 0.8922 | 0.9381 |
| Random Forest | SMOTE Oversampled | 0.9903 | 0.9984 | 0.9823 | 0.9903 |

---

## Observations

* Original data models show extremely high accuracy (~0.999) but poor recall in some cases (e.g., Logistic Regression recall = 0.5667), indicating class imbalance affects fraud detection.
* Downsampled models slightly reduce accuracy but improve recall and F1 scores (e.g., Decision Tree F1 = 0.9146), providing better class balance.
* SMOTE oversampling gives the best overall performance, with very high precision and recall (e.g., Decision Tree F1 = 0.9983, Random Forest F1 = 0.9903).
* Random Forest consistently outperforms other models in F1 score across datasets, showing strong ability to detect complex fraud patterns.

---

## Conclusion

* Accuracy alone can be misleading in imbalanced datasets; recall and F1 score are key metrics for fraud detection.
* SMOTE oversampling effectively balances classes, achieving near-perfect detection with high precision and recall.
* Random Forest with SMOTE is the most effective model, achieving an F1 score of 0.9903, making it highly reliable for detecting fraudulent transactions.
