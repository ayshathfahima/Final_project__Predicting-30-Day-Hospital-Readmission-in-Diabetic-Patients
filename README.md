# 🏥 Final Project: Diabetes Readmission Prediction

This project builds and evaluates machine learning models to predict whether a **diabetic patient will be readmitted within 30 days after hospital discharge**.  
It uses the **Diabetes 130-US hospitals dataset** from the UCI Machine Learning Repository.

---

## 📌 Project Overview

Hospital readmissions are costly and impact patient care quality. Identifying patients at risk of **early readmission (<30 days)** helps improve healthcare outcomes and optimize hospital resources.

This project follows the complete ML pipeline:

1. **Data Preprocessing**
2. **Exploratory Data Analysis (EDA) & Visualization**
3. **Feature Selection**
4. **Model Building & Evaluation**
5. **Results Summary**

---

## 📂 Dataset

- **Source:** [UCI Diabetes 130-US hospitals dataset](https://archive.ics.uci.edu/ml/datasets/diabetes+130-us+hospitals+for+years+1999-2008)
- **Records:** ~100,000 patient encounters
- **Target Variable:**  
  - `readmitted = 1` → Readmitted within 30 days  
  - `readmitted = 0` → No readmission or readmitted after 30 days  

---

## ⚙️ Data Preprocessing

- Dropped **ID columns**: `encounter_id`, `patient_nbr`
- Replaced missing values (`?`) with `NaN`
- Encoded target variable:
  - `<30` → `1`
  - `NO` or `>30` → `0`
- Removed columns with **>50% missing values**
- Filled missing values using **mode**
- Converted categorical variables into **dummy variables**
- Final preprocessed dataset was saved as: preprocessed_diabetic_data.csv


## 📊 Exploratory Data Analysis (EDA)

### Class Balance
- Imbalanced target variable (majority = not readmitted)
- Visualized using `seaborn.countplot`

### Feature Importance
- Selected **Top 30 features** using `mutual_info_classif`
- Visualized with `seaborn.barplot`

---

## 🔑 Feature Selection

- **Variance Threshold** → removed low-variance features
- **SelectKBest (Mutual Information)** → kept top 30 most informative features

---

##  Models Implemented

The following machine learning models were trained and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

---

## 📈 Results Summary

| Model               | Accuracy | Precision | Recall | F1 Score |
|----------------------|----------|-----------|-----------|----------|
| Logistic Regression |0.886662   |0.461538   |0.013675   |0.026563     
| Decision Tree       |0.792268   |0.149403   |0.178348   |0.162597
| Random Forest       |0.883634   |0.296000   |0.021083   |0.039362      
| Gradient Boosting   |0.886985   | 0.510638  |0.013675   |0.026637     

👉 **Random Forest / Gradient Boosting performed best** on this dataset.

---

