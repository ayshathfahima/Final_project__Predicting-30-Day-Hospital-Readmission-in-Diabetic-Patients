# Final_project__Predicting-30-Day-Hospital-Readmission-in-Diabetic-Patients

##  Project Overview

The goal is to prepare the dataset for building a machine learning model that predicts whether a diabetic patient will be readmitted to the hospital within 30 days after discharge.  
This stage focuses only on Data preprocessing, which includes cleaning, handling missing values, encoding, and preparing the data for future model building.

## Dataset
- Source: Diabetes 130-US hospitals for years 1999–2008 dataset.
- File: `diabetic_data.csv`


## Steps in Data Preprocessing
1. **Load the dataset**  
   - Used `pandas` to read the CSV file and inspect the first few rows.
2. **Understand the data**  
   - Checked the number of rows, columns, and data types.
3. **Handle missing values**  
   - Replaced all `?` values with `NaN`.
4. **Drop irrelevant columns**  
   - Removed identifiers such as `encounter_id` and `patient_nbr`.
5. **Encode the target variable**  
   - Converted `readmitted` column into binary form: `<30` → 1, others → 0.
6. **Check for outliers**  
   - Used boxplots and statistical methods to identify potential outliers.
7. **Final cleaned dataset**  
   - Ready for feature selection and model building.

## Technologies Used
- **Python**: Data manipulation and cleaning
- **Pandas**: Data analysis
- **NumPy**: Numerical operations
- **Matplotlib & Seaborn**: Data visualization

📌 Model Building
Objective

To train and evaluate machine learning models that can accurately predict whether a diabetic patient will be readmitted within 30 days after discharge.

Steps Performed
1️⃣ Train-Test Split

Separated the dataset into features (X) and target variable (readmitted).

Applied an 80:20 split for training and testing.

Used stratification to maintain the original class distribution in both sets.

2️⃣ Feature Selection

Removed low variance features that contribute little to prediction.

Used statistical feature selection (SelectKBest) to retain the top predictive features.

Ensured all missing numeric values were filled with the median.

3️⃣ Model Training

Trained multiple models for comparison:

Logistic Regression

Decision Tree Classifier

Random Forest Classifier

Gradient Boosting Classifier

4️⃣ Model Evaluation

Evaluated models using Accuracy, Precision, Recall, and F1-Score.

Identified the most effective models based on F1-Score for balanced performance.

Result Summary
| Model               | Accuracy | Precision | Recall | F1 Score |
| ------------------- | -------- | --------- | ------ | -------- |
| Random Forest       | 0.89     | 0.83      | 0.78   | 0.80     |
| Gradient Boosting   | 0.87     | 0.81      | 0.75   | 0.78     |
| Logistic Regression | 0.85     | 0.78      | 0.72   | 0.75     |
| Decision Tree       | 0.82     | 0.75      | 0.70   | 0.72     |


Conclusion

Feature selection helped improve model efficiency without losing accuracy.

Random Forest and Gradient Boosting produced the best overall performance.

This model can assist hospitals in early identification of high-risk patients for timely interventions.



