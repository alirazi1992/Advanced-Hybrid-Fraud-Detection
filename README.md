# 🕵️‍♂️ Day 13 — Advanced Hybrid Fraud Detection

This project is part of my **30 Days of Data Science & Machine Learning** challenge.  
In this project, I developed a **fraud detection system** using **hybrid feature engineering**, **resampling techniques**, and **XGBoost**, along with **explainability (SHAP)** for model transparency.

---

## 📂 Dataset
- **Credit Card Fraud Dataset**
- Highly imbalanced:
  - Legitimate transactions ≈ 99.83%
  - Fraud transactions ≈ 0.17%
- Features:
  - `V1–V28`: PCA-transformed features
  - `Amount`: Transaction value
  - `Class`: Target (0 = Normal, 1 = Fraud)

---

## 🛠️ Workflow Overview
1. **Data Preparation**
   - Handle imbalance using SMOTE + undersampling (hybrid approach)
   - Min-max normalization
   - Additional engineered risk-features

2. **Modeling**
   - Isolation Forest
   - Local Outlier Factor
   - Random Forest
   - **XGBoost (Final Model)**

3. **Evaluation Metrics**
   - Precision
   - Recall (prioritized)
   - F1 Score
   - ROC-AUC

4. **Explainability**
   - SHAP summary plots to interpret model decisions

---

## 📈 Results

| Model | Precision | Recall | F1 Score | ROC-AUC |
|------|-----------|--------|---------|---------|
| Isolation Forest | 0.256 | 0.256 | 0.256 | 0.945 |
| Local Outlier Factor | 0.000 | 0.000 | 0.000 | 0.513 |
| **XGBoost (Hybrid Feats)** | **Best Balance** | **High Recall** | **Strong Performance** | **✔ Top Model** |

> In fraud detection, **recall is more critical** than precision — catching fraudulent activity matters more than occasional false alarms.

---

## 🔍 Explainability (SHAP)
- Identifies most influential features driving fraud predictions.
- Builds **trust** and supports **auditing** in financial systems.

---

## 🚀 How to Run

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
jupyter notebook Day13_Fraud_Advanced_Hybrid.ipynb
```
