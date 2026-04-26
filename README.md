# Data Cleanser

## Overview

This project focuses on cleaning and preparing a healthcare dataset for machine learning. The dataset contains patient demographic details, medical attributes, and a target variable indicating disease risk. The main objective is to handle missing values and outliers using various techniques and compare their effectiveness.

---
### Video Explaination:
https://drive.google.com/file/d/1A8pgGUuM3BWtCp4gqAYBRWEwOmooGNIA/view?usp=drive_link
## Dataset Description

The dataset includes the following features:

- **patient_id**: Unique identifier for each patient  
- **age**: Age of the patient  
- **gender**: Male / Female  
- **region**: North / South / East / West  
- **bmi**: Body Mass Index  
- **blood_pressure**: Systolic blood pressure (mmHg)  
- **cholesterol**: Cholesterol level (mg/dL)  
- **glucose**: Fasting glucose level (mg/dL)  
- **disease_risk**: Target variable (0 = Low Risk, 1 = High Risk)  

The dataset contains **missing values and outliers**, which are handled in this project.

---

## Objectives

- Identify and analyze missing values  
- Apply different imputation techniques  
- Detect and treat outliers using statistical methods  
- Compare results of different techniques  
- Generate a final cleaned dataset ready for machine learning  

---

## Part A: Handling Missing Values

The following techniques were applied:

### 1. Simple Imputer (Numerical)
- Used **median** to fill missing values in numerical columns  
- Robust to outliers  

### 2. Simple Imputer (Categorical)
- Used **most frequent value (mode)** for categorical columns  

### 3. Most Frequent Imputation
- Applied specifically to the `gender` column  

### 4. Missing Indicator + Random Sampling
- Created indicator columns to track missing values  
- Used random sampling to preserve data distribution  

### 5. KNN Imputer
- Used nearest neighbors to estimate missing values  
- Considered relationships between multiple features  

### 6. MICE Algorithm
- Used iterative modeling to fill missing values  
- Provided more accurate but computationally expensive results  

---

## Part B: Handling Outliers

Outliers were detected and treated using the following methods:

### 1. Z-Score Method
- Identified values far from the mean  
- Removed values with |Z| > 3  

### 2. IQR Method
- Used quartiles to detect extreme values  
- Removed values outside 1.5 × IQR range  

### 3. Percentile Method
- Capped values below 1st percentile and above 99th percentile  
- Preserved dataset size  

### 4. Winsorization
- Replaced extreme values with percentile boundaries  
- Reduced impact of outliers without removing data  

---

## Comparison of Methods

| Method        | Removes Data | Preserves Shape | Complexity |
|--------------|------------|----------------|------------|
| Z-score       | Yes        | No             | Low        |
| IQR           | Yes        | No             | Low        |
| Percentile    | No         | Yes            | Low        |
| Winsorization | No         | Yes            | Medium     |

---

## Final Clean Dataset

The final dataset was created using:

- **Median imputation** for numerical features  
- **Mode imputation** for categorical features  
- **IQR method** for outlier removal  

### Result:
- All missing values handled  
- Outliers removed effectively  
- Dataset ready for machine learning  

---

## Conclusion

Data preprocessing significantly improved the dataset quality by handling missing values and outliers. Simple and robust methods such as median imputation and IQR-based outlier removal provided the best balance between accuracy and efficiency. The final dataset is clean, consistent, and suitable for predictive modeling tasks such as disease risk classification.

---

## Technologies Used

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- SciPy  
- Matplotlib  

---

## How to Run

1. Install required libraries:
   ```bash
   pip install pandas numpy scikit-learn scipy matplotlib
