# Diabetes Prediction using Machine Learning

## Project Overview
This project builds machine learning models to predict whether an individual has diabetes using demographic, clinical, and lifestyle features.

The goal is to develop a **screening-oriented model** that prioritizes **recall**, minimizing missed diabetic cases while maintaining a reasonable balance with precision.

---

## Dataset
- **Size:** 100,000 patient records  
- **Features:** 16 variables (demographic, clinical, medical history)  
- **Target:** Diabetes (0 = No, 1 = Yes)  
- **Class imbalance:** ~8.5% positive cases  

### Feature categories:
- **Demographic:** age, gender, location, race  
- **Clinical:** BMI, HbA1c level, blood glucose level  
- **Medical history:** hypertension, heart disease, smoking history  

The dataset exhibits strong class imbalance, making accuracy alone an unreliable evaluation metric.

---

## Exploratory Data Analysis
Key findings:
- Older individuals show higher diabetes prevalence  
- Higher BMI is associated with increased risk  
- HbA1c and blood glucose are strong predictors  
- Hypertension and heart disease correlate with diabetes  
- Some variables (e.g., year, race) show limited predictive value  

---

## Feature Engineering
- Encoded categorical variables (gender, smoking history)  
- Removed low-impact features (e.g., year, location)  
- Handled BMI outliers (capping at 99th percentile)  
- Created age-group features  
- Final dataset: **~100,000 rows, 14 numeric features**  

---

## ⚙️ Methodology

### Train-Test Setup
- 80/20 stratified split  
- 5-fold cross-validation  

### Handling Class Imbalance
Tested:
- Class weighting (selected)
- Random undersampling  
- SMOTE  

### Models Compared
- Logistic Regression  
- Decision Tree  
- Random Forest  
- XGBoost  

---

## Model Evaluation

Metrics used:
- **Recall (priority)**  
- Precision  
- F1-score  
- ROC curve  
- Precision-Recall curve  

---

## Final Model

**Random Forest with threshold tuning**

- Achieved high recall (~0.92), effectively minimizing missed diabetic cases  
- Maintains a strong balance between false positives and false negatives  
- Demonstrates strong generalization with minimal overfitting  

This makes the model suitable for **real-world screening applications**, where identifying as many true cases as possible is critical.

---

## Key Insights
- Class imbalance must be handled carefully in healthcare applications  
- Recall is more important than accuracy in screening tasks  
- Threshold tuning significantly improves practical model performance  
- HbA1c, glucose, BMI, and age are key predictors of diabetes  

---

## Limitations
- Includes diagnostic features (HbA1c, glucose), which may inflate performance  
- Real-world screening models should rely on earlier-stage features  
- Model performance may vary across different populations  

---

## Future Improvements
- Remove diagnostic leakage features  
- Validate on external datasets  
- Explore model interpretability (e.g., SHAP)  
- Develop deployment-ready pipelines  

---

## Project Structure

The repository is organized as follows:

```text
diabetes-prediction-ml/
│
├── data/
│   └── diabetes_dataset.csv
│
├── notebooks/
│   ├── 01_eda.ipynb              # Exploratory Data Analysis
│   └── 02_modeling.ipynb         # Modeling and evaluation
│
├── reports/
│   ├── diabetes_prediction_paper.pdf
│   └── diabetes_prediction_presentation.pdf
│
└── README.md
