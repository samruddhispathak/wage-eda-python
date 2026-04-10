<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)]()
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)]()
[![Seaborn](https://img.shields.io/badge/Seaborn-Visualisation-4C72B0?style=for-the-badge)]()
[![Statsmodels](https://img.shields.io/badge/Statsmodels-Regression-A855F7?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Completed-A855F7?style=for-the-badge)]()

</div>

---

## 📌 Project Overview

This project performs a full **Exploratory Data Analysis (EDA)** on a wage dataset to uncover the relationships between hourly earnings and demographic, educational, and employment-related factors. The analysis is grounded in **labour economics** and directly relevant to **HR analytics** and **people data science**.

> 🎯 **Goal:** Use EDA to convert raw data into actionable insights about wage dynamics, identify key predictors of earnings, and support data-driven HR and policy decisions.

---

## 📂 Dataset

| Detail | Info |
|--------|------|
| Total Records | 525 individuals |
| Key Variables | Hourly Wage, Years in Education, Years in Employment, Marital Status, Gender, Race, Number of Dependents |
| Missing Values | Treated using forward fill (`ffill()`) |

---

## 🔍 Project Structure

### 1. Descriptive Statistics
- Mean hourly wage: **~$5.92** · Range: $0.53 – $24.98
- Average education: **12.6 years** (clustered at 12–14 years)
- Employment experience: **0–44 years** (highly variable)
- Over 60% of individuals are married

### 2. Missing Value Treatment
- Identified gaps across all 7 variables
- Applied **forward fill** to maintain realistic distributions
- Verified zero nulls after cleaning

### 3. Data Visualisation

| Chart | Purpose | Key Finding |
|-------|---------|-------------|
| Histogram (Wage Distribution) | Understand wage spread | Right-skewed — most earn lower wages, few earn high |
| Scatter Plot (Wage vs Education) | Education-wage relationship | Positive trend — more education → higher wage |
| Box Plot (Wage by Gender) | Gender wage comparison | Males have higher median wage |
| Heatmap (Correlation Matrix) | Multivariate relationships | Education (0.38) & experience (0.35) correlate with wage |
| KDE Plot (Wage by Race) | Race-wage distribution | White workers show slightly higher wage distribution |

### 4. Unique Value Frequency Analysis
- **Gender:** Male 275 · Female 250 — near balanced
- **Race:** White 469 · Non-white 56 — imbalanced (noted as limitation)

### 5. Chi-Square Test — Gender vs Race Independence
- **H₀:** Gender and race are independent
- Chi-square = 0.002 · **p-value = 0.962**
- ✅ Fail to reject H₀ — no significant association between gender and race

### 6. Subset Analysis with Logical Conditions
- **Subset 1:** Males earning above median wage (n=181)
  - Mean wage: $8.93 · Mean education: 13.4 years · ~80% married
- **Subset 2:** Highly educated + experienced workers (n=39)
  - Mean wage: ~$10 · Average education: ~15 years · Average experience: 18 years

### 7. T-Test — High Wage vs Low Wage Groups
- **T-statistic: 21.11** · **p-value < 0.00001**
- ✅ Reject H₀ — significant difference in mean wages between groups

### 8. Grouped Summary by Gender
| Metric | Female | Male |
|--------|--------|------|
| Mean Wage | $4.65 | $7.10 |
| Median Wage | $3.75 | $6.00 |
| Mean Education | 12.3 yrs | 12.8 yrs |
| Mean Experience | 3.7 yrs | 6.4 yrs |

> 💡 Education levels are nearly equal — the wage gap is largely driven by **differences in work experience**, not education.

### 9. Linear Regression — Wage Predictors
- **Dependent variable:** Hourly Wage
- **Predictors:** Years in Education + Years in Employment
- Education coefficient: **+$0.55 per additional year**
- Experience coefficient: **+$0.19 per additional year**
- **R² = 0.287** — model explains ~29% of wage variation
- Both predictors statistically significant (p < 0.001)

### 10. Regression Diagnostics
- Actual vs Fitted Values plot — positive trend confirmed
- Residuals vs Fitted — slight heteroscedasticity at higher wages
- Histogram of residuals — approximately normal
- Q–Q plot — mild deviation suggesting heavier tails

---

## 🏆 Key Findings

- Wages are **right-skewed** — income inequality is visible in the data
- **Education and experience** are the two strongest wage predictors
- The **gender wage gap** is driven more by experience differences than education
- **Dependents have no meaningful impact** on wage levels
- The regression model is significant but explains only ~29% of variance — other factors (industry, job type, location) likely play a major role

---

## 🛠️ Libraries Used

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy.stats import norm, gaussian_kde, chi2_contingency
from scipy import stats
import statsmodels.api as sm
import warnings
```

---

## 💼 HR Analytics Relevance

This project mirrors real-world HR analytics tasks including compensation benchmarking, pay equity analysis, workforce segmentation, and regression-based salary modelling — directly applicable to roles in people analytics and HR data science.

---

## 👩‍💻 Author

**Samruddhi Pathak**
MSc Business Analytics · Aston University, Birmingham

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/samruddhi-pathak-0412s)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/samruddhispathak)

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer&animation=twinkling" width="100%"/>
</div>
