🏥 Diabetes Readmission Prediction – Final Project

This project builds and evaluates machine learning models to predict whether a diabetic patient will be readmitted within 30 days after hospital discharge. It uses the Diabetes 130-US hospitals dataset from the UCI Machine Learning Repository.

📌 Project Overview

Hospital readmissions are costly and impact patient care quality. Identifying patients at risk of early readmission (<30 days) helps improve healthcare outcomes and optimize hospital resources.

This project follows a complete ML pipeline:

Data Preprocessing

Exploratory Data Analysis (EDA) & Visualization

Outlier Detection

Feature Selection

Model Building & Evaluation

Hyperparameter Tuning & Model Comparison

Final Model Selection & Interpretation

📂 Dataset

Source: UCI Diabetes 130-US hospitals dataset

Records: ~100,000 patient encounters

Target Variable:

readmitted = 1 → Readmitted within 30 days

readmitted = 0 → No readmission or readmitted after 30 days

⚙️ Data Preprocessing

Dropped ID columns: encounter_id, patient_nbr

Replaced missing values (?) with NaN

Encoded target variable:

<30 → 1

NO or >30 → 0

Removed columns with >50% missing values

Filled remaining missing values using mode

Converted categorical variables into dummy variables

Final preprocessed dataset saved as: preprocessed_diabetic_data.csv

📊 Exploratory Data Analysis (EDA)
Class Balance

Imbalanced target variable (majority = not readmitted)

Visualized using seaborn.countplot

Feature Importance

Selected Top 30 features using mutual_info_classif

Visualized with seaborn.barplot

📈 Outlier Detection

Outliers were analyzed in key numeric features:

number_inpatient

number_emergency

number_outpatient

Methods Used

Boxplots → Visual identification of extreme values

Interquartile Range (IQR) method → Counted outliers

🔎 Observations

All three numeric features showed the presence of extreme values

Outliers were kept for modeling since they represent real variations in patient visits and are important for predicting readmission risk

Note: Handling outliers carefully ensures the model learns from true high-risk patient patterns.

🔑 Feature Selection

Variance Threshold → removed low-variance features

SelectKBest (Mutual Information) → retained top 30 most informative features

🤖 Models Implemented

The following machine learning models were trained and evaluated before hyperparameter tuning:
| Model               | Accuracy | Precision | Recall   | F1 Score |
| ------------------- | -------- | --------- | -------- | -------- |
| Decision Tree       | 0.798582 | 0.166098  | 0.194302 | 0.179097 |
| Random Forest       | 0.887693 | 0.615385  | 0.018234 | 0.035418 |
| Gradient Boosting   | 0.887371 | 0.585366  | 0.013675 | 0.026726 |
| Logistic Regression | 0.886920 | 0.000000  | 0.000000 | 0.000000 |


🔎 Observations

Random Forest and Gradient Boosting performed best before tuning

Decision Tree had lower accuracy but is simpler and interpretable

Logistic Regression had very low recall and F1, so not suitable at this stage

⚡ Hyperparameter Tuning (GridSearchCV)

After tuning hyperparameters, the accuracies were:

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 0.8869   |
| Decision Tree       | 0.8869   |
| Random Forest       | 0.8868   |
| Gradient Boosting   | 0.8867   |

🔎 Observations

Decision Tree and Logistic Regression achieved the same top accuracy (0.8869)

Random Forest and Gradient Boosting were very close but slightly lower

Final Choice: Decision Tree Classifier

Comparable accuracy to the best models

Simple and interpretable (important in healthcare)

Computationally faster than Random Forest and Gradient Boosting

📊 Final Model: Decision Tree Classifier
✅ Predictions

First few predictions vs actual values were compared

Classification Report and Confusion Matrix were used to evaluate performance

🌟 Feature Importance

Key features contributing to 30-day readmission:

Feature	Importance
number_inpatient	0.7420
discharge_disposition_id	0.2580

Interpretation:
Patients with more prior inpatient visits and specific discharge methods are at higher risk of being readmitted within 30 days. Hospitals can use this insight to prioritize monitoring and post-discharge care.

🎯 Conclusion

This project successfully developed a machine learning model to predict hospital readmissions within 30 days for diabetic patients.

Key Points:

Decision Tree Classifier selected as the final model

Strong accuracy while remaining simple and interpretable

Outlier analysis ensures model captures true high-risk patient patterns

Key features like prior inpatient visits and discharge disposition guide healthcare interventions

Impact: Hospitals can leverage these insights to reduce readmission rates and improve patient care quality.
