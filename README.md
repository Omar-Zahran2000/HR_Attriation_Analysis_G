# Employee Attrition Analysis - Salifort Motors

## Problem Statement

Salifort Motors, a mid-sized automotive manufacturer, faces a high employee turnover rate. Understanding the drivers behind employee attrition is critical to improve retention and reduce hiring costs.

This project aims to:
- Identify key factors that contribute to attrition.
- Build predictive models to classify whether an employee is likely to leave.
- Provide actionable business recommendations based on the analysis.

---

## Dataset Overview

The dataset contains anonymized HR data for 12,000+ employees, including:
- Demographic and performance metrics (e.g., satisfaction level, last evaluation).
- Work-related features (e.g., average monthly hours, tenure, number of projects).
- Organizational data (e.g., department, salary level, promotion history).
- Target variable: `left` (0 = stayed, 1 = left)

---

##  Methodology

The workflow includes:

1. **Exploratory Data Analysis (EDA)**
   - Outlier detection
   - Department-level attrition trends
   - Relationships between features like tenure, satisfaction, and workload

2. **Feature Engineering**
   - Created binary flags like `overworked` for monthly hours > 175
   - Encoded categorical variables (e.g., department, salary)
   - Checked for data leakage via `last_evaluation` insights

3. **Modeling Techniques**
   - Logistic Regression
   - Decision Tree (pre- and post-feature engineering)
   - Random Forest with GridSearchCV (Round 1 and Round 2)

4. **Evaluation Metrics**
   - Accuracy, Precision, Recall, F1-score
   - ROC-AUC
   - Confusion Matrices

---

##  Key Visualizations

###  Satisfaction by Tenure
![alt text](output_52_0.png)

###  Attrition by Department
![alt text](output_38_0.png)

###  Monthly Hours vs Satisfaction Level
![alt text](output_60_0.png)

###  Correlation Heatmap
![alt text](output_73_0.png)

---

##  Model Performance Summary

| Model                     | Accuracy | Precision | Recall | F1-score | AUC   |
|--------------------------|----------|-----------|--------|----------|-------|
| Logistic Regression      | 83.0%    | 80.0%     | 83.0%  | 80.0%    | -     |
| Decision Tree (Round 1)  | 97.2%    | 91.5%     | 91.7%  | 91.6%    | 96.98%|
| Random Forest (R1 - Test)| **98.1%**| **96.4%** | **91.9%**| **94.1%**| **95.64%** |
| Random Forest (R2 - Test)| 96.2%    | 87.0%     | 90.4%  | 88.7%    | 93.84%|

**Best Model:** The Round 1 Random Forest model outperformed all others across all key metrics.

---

## Business Recommendations

- **Limit Project Load**: Cap project assignments to reduce burnout.
- **Improve Promotion Policies**: Employees with no promotion in 5 years are more likely to leave.
- **Clarify Overtime Expectations**: Many leavers worked >200 hours/month.
- **Address Tenure Dissatisfaction**: Employees with 2–4 years of service show higher attrition.
- **Evaluate Evaluation Bias**: Over-reliance on `last_evaluation` may mask true performance trends.

---

## Next Steps
- Build a dashboard for real-time attrition risk monitoring.
- Remove `last_evaluation` in alternative models to check for leakage.


