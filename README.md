# Credit Card Fraud Detection

## Overview
This project focuses on detecting fraudulent credit card transactions using machine learning. We evaluate **Decision Tree**, **Random Forest**, and **Logistic Regression** models on three different datasets:

1. **Original Dataset** – The raw dataset.
2. **Downsampled Dataset** – Balanced by downsampling normal transactions.
3. **SMOTE Oversampled Dataset** – Balanced using SMOTE (Synthetic Minority Oversampling Technique).

The goal is to accurately classify transactions as **Normal (0)** or **Fraud (1)**.

---

## Dataset
- Source: [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Features: 30 anonymized numerical features (`V1`–`V28`, `Time`, `Amount`) and a target class `Class` (0 = Normal, 1 = Fraud)
- No missing values in the dataset.

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
- **Accuracy** – Overall correctness
- **Precision** – Correctly predicted fraud out of all predicted fraud
- **Recall** – Correctly predicted fraud out of all actual fraud
- **F1 Score** – Harmonic mean of precision and recall
- **Confusion Matrix** – Visual representation of correct and incorrect predictions

---

## Installation

```bash
# Clone the repository
git clone <your-repo-link>

# Install dependencies
pip install -r requirements.txt

---

## Results

Confusion Matrices:
1. Decision Tree:
<img width="518" height="516" alt="image" src="https://github.com/user-attachments/assets/806058b0-08bc-4aba-ba92-ce21294c1974" />
<img width="515" height="489" alt="image" src="https://github.com/user-attachments/assets/00ff950b-c70d-434b-ae7b-58067c813024" />
<img width="573" height="498" alt="image" src="https://github.com/user-attachments/assets/f697bb1a-5f0a-4f7f-b19f-0754db91f885" />
2. RandomForest:
<img width="569" height="489" alt="image" src="https://github.com/user-attachments/assets/c45cf266-e680-48ec-8acc-675535799d9b" />
<img width="471" height="499" alt="image" src="https://github.com/user-attachments/assets/b7a77d58-ead8-4cfa-858d-e496ce3191c0" />


3. Logistic Regression:





---

## Observations & Conclusions

