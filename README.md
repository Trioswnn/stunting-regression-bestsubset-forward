# Stunting Prevalence Analysis in East Java

## Author
**Trio Setiawan**  
Applied Data Science, Politeknik Elektronika Negeri Surabaya (PENS)

---

## Overview
This project analyzes district-level stunting prevalence in East Java using multiple linear regression and formal variable selection techniques. The objective is to identify the most influential public health indicators associated with stunting prevalence and compare different statistical model selection approaches.

The analysis applies:
- Best Subset Regression
- Forward Selection
- Backward Elimination
- OLS Assumption Testing
- VIF Analysis
- Standardized Robustness Checks

---

## Problem Statement
Stunting remains one of the most critical indicators of chronic malnutrition in Indonesia. Despite improvements in healthcare access, stunting prevalence varies substantially across districts in East Java.

This project aims to answer the following question:

> Which district-level health indicators best explain variations in stunting prevalence across East Java?

---

## Dataset Information
- Dataset: Health Indicators of Districts/Cities in East Java
- Observations: 38 districts/cities
- Candidate Predictors: 10 theory-driven health indicators
- Target Variable: `stunting_pct`

The predictors represent multiple public health dimensions:
- Acute malnutrition
- Birth outcomes
- Breastfeeding practices
- Child health services
- Nutrition monitoring
- Sanitation & WASH

---

## Methodology

### 1. Data Preprocessing
- Missing value analysis
- Median imputation
- Feature selection based on domain knowledge
- Z-score standardization for robustness checks

### 2. Exploratory Data Analysis (EDA)
- Distribution analysis
- Boxplots for outlier detection
- Correlation heatmap
- Scatterplots between predictors and target

### 3. Regression Modeling
- Baseline OLS Regression
- Best Subset Regression
- Forward Stepwise Selection
- Backward Elimination

### 4. Model Evaluation
Models were compared using:
- Adjusted R²
- RMSE
- AIC
- BIC
- Mallows’ Cₚ
- Statistical significance of coefficients

### 5. Statistical Diagnostics
- Residual diagnostics
- Shapiro-Wilk normality test
- Breusch-Pagan heteroscedasticity test
- Variance Inflation Factor (VIF) analysis

### 6. Robustness Check
A standardized regression model was fitted to:
- Evaluate coefficient stability
- Reduce condition number
- Compare standardized beta coefficients

---

## Key Findings
- Wasting percentage was identified as the strongest predictor of stunting prevalence.
- Forward Selection and Best Subset Regression converged on the same final model.
- The recommended model achieved:
  - Adjusted R² = 0.389
  - RMSE = 3.654
- OLS assumptions were satisfied based on:
  - Shapiro-Wilk test
  - Breusch-Pagan test
- Standardization reduced the condition number by 99.9%, indicating scale-related instability rather than severe multicollinearity.

---

## Final Recommended Model
```python
stunting_pct ~ wasting_pct
              + infant_health_service_pct
              + sanitary_toilet_pct
              + low_birth_weight_pct
```

---

## Technologies Used
- Python
- Pandas
- NumPy
- Statsmodels
- Scikit-learn
- SciPy
- Matplotlib
- Seaborn

---

## How to Run
Clone this repository:

```bash
git clone https://github.com/your-username/stunting-regression-analysis.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook
```

---

## Future Improvements
Potential future enhancements include:
- Cross-validation for model generalization
- Regularized regression (Lasso/Ridge)
- Spatial regression analysis
- Tree-based model comparison
- Larger longitudinal datasets
