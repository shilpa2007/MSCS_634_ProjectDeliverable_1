# MSCS 634 — Project Deliverable 1
# Data Collection, Cleaning, and Exploration

**Name:** Shilpa Mesineni  
**Course:** MSCS 634 – Advanced Data Mining and Big Data Analytics

---

## Dataset Summary

**Dataset:** Pima Indians Diabetes Dataset  
**Source:** UCI Machine Learning Repository / Kaggle  
**Records:** 768 patients  
**Features:** 9 attributes (8 physiological measurements + 1 binary outcome)  

| Feature | Description |
|---------|-------------|
| Pregnancies | Number of pregnancies |
| Glucose | Plasma glucose concentration (mg/dL) |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skinfold thickness (mm) |
| Insulin | 2-hour serum insulin (μU/mL) |
| BMI | Body mass index (kg/m²) |
| DiabetesPedigreeFunction | Hereditary diabetes likelihood score |
| Age | Patient age (years) |
| Outcome | Diabetes diagnosis (1=Yes, 0=No) |

---

## Key Insights from EDA

1. **Glucose is the strongest predictor** of diabetes (correlation = 0.49 with Outcome)
2. **BMI and Age** are the next most important features for distinguishing diabetic from non-diabetic patients
3. **Diabetic patients consistently show** higher Glucose, BMI, Insulin, and Age across all analyses
4. **Diabetes rate increases sharply with age** — from 24% in the 21-30 group to 58% in the 51-60 group
5. **SkinThickness and BMI** are correlated (0.57) — multicollinearity to monitor in regression models
6. **Age and Pregnancies** are moderately correlated (0.54) — biologically expected

---

## Data Cleaning Steps

1. **Zero-value replacement:** Five features (Glucose, BloodPressure, SkinThickness, Insulin, BMI) used 0 as a placeholder for missing values — replaced with NaN for honest treatment
2. **Class-wise median imputation:** Missing values filled with the median grouped by Outcome class (diabetic vs non-diabetic) to preserve biological group differences
3. **Duplicate removal:** No duplicates found in this dataset
4. **Outlier capping:** Applied 3×IQR Winsorization — extreme values capped rather than removed to preserve sample size (Insulin and DiabetesPedigreeFunction had most outliers)

---

## Challenges and Decisions

- **Insulin had 48.7% missing values** — simple global median would flatten the group difference; class-wise median was chosen to preserve clinically meaningful distinctions
- **Zero-coded missing values** required domain knowledge to identify — a purely statistical approach would have missed them
- **Outlier treatment:** Removal vs. capping — removal would have lost ~5% of data; Winsorization preserves records while bounding extreme values

---

## Files in this Repository

| File | Description |
|------|-------------|
| `MSCS_634_ProjectDeliverable_1.ipynb` | Jupyter Notebook with all code and visualizations |
| `pima_diabetes_cleaned.csv` | Cleaned dataset saved for use in Deliverable 2 |
| `README.md` | This file |
| `screenshots/` | All visualization screenshots (PNG files) |
