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


