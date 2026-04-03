# Diabetes Prediction using Machine Learning

## Overview
This project builds machine learning models to predict whether an individual has diabetes using demographic, clinical, and lifestyle features.

The goal is to develop a high-recall screening model that minimizes missed diabetic cases while maintaining reasonable precision.

---

## Dataset
- 100,000 patient records
- 16 features (demographic, clinical, medical history)
- Target: Diabetes (0 = No, 1 = Yes)
- Strong class imbalance (~8.5% positive)

---

## Key Steps

### 1. Exploratory Data Analysis
- Identified relationships between:
  - Age, BMI, HbA1c, blood glucose
- Observed strong class imbalance

### 2. Feature Engineering
- Encoded categorical variables
- Removed low-impact features
- Handled outliers (BMI capping)
- Created age groups

### 3. Handling Class Imbalance
Tested:
- Class weighting (final choice)
- Undersampling
- SMOTE

---

## Models
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost

---

## Model Evaluation
Metrics used:
- Recall (priority)
- Precision
- F1-score
- ROC / PR curves

---

## Final Model
**Random Forest with threshold tuning**

- Achieved high recall (~0.92)
- Best balance between false positives and false negatives
- Strong generalization (minimal overfitting)

---

## Project Structure
```text
diabetes-prediction-ml/
│
├── data/
│   └── diabetes_dataset.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   └── 02_modeling.ipynb
│
├── reports/
│   ├── diabetes_prediction_paper.pdf
│   └── diabetes_prediction_presentation.pdf
│
└── README.md
