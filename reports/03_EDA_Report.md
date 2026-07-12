# Exploratory Data Analysis (EDA) Report

## Objective

The objective of exploratory data analysis (EDA) is to understand the characteristics of the cleaned IBM HR Employee Attrition dataset and identify patterns in employee attrition. To examine relationships between variables and generate insights that support business decision-making and dashboard development.

---

## Dataset Overview

The exploratory analysis was performed on the cleaned dataset containing:

- Number of Records: **1470**
- Number of Features: **31**

This analysis includes univariate analysis, bivariate analysis, correlation analysis and outlier analysis.

---

## Exploratory Data Analysis

### 1. Target Variable Analysis

The distribution of the target variable (Attrition) was examined to understand employee retention.

**Observation**

- Employees who stayed in the organization were significantly higher than employees who left.
- Approximately **83.88%** of employees stayed, while **16.12%** left the organization.

---

### 2. Univariate Analysis

Univariate analysis was performed to study the distribution of individual variables.

The following variables were analyzed:

- Age
- Monthly Income
- Total Working Years
- Distance From Home
- Department
- Job Role
- Gender
- Marital Status
- Business Travel
- OverTime
- Education
- Job Level
- Job Satisfaction
- Environment Satisfaction
- Work-Life Balance

**Key Observations**

- The majority of employees belonged to the Research & Development department.
- Sales Executive was the most common job role.
- Most employees did not work overtime.
- Most employees travelled rarely for business.
- Employee ages were concentrated more in the younger and middle-age groups.
- Monthly income and total working years showed right-skewed distributions.

---

### 3. Bivariate Analysis

Bivariate analysis was performed to study the relationship between employee attrition and other variables.

The following relationships were analyzed:

- OverTime vs Attrition
- Department vs Attrition
- Job Role vs Attrition
- Gender vs Attrition
- Marital Status vs Attrition
- Business Travel vs Attrition
- Education vs Attrition
- Job Level vs Attrition
- Job Satisfaction vs Attrition
- Environment Satisfaction vs Attrition
- Work-Life Balance vs Attrition
- Age vs Attrition
- Monthly Income vs Attrition
- Total Working Years vs Attrition
- Distance From Home vs Attrition

**Key Observations**

- Employees working overtime showed comparatively higher attrition.
- Research & Development recorded the highest attrition count among departments.
- Laboratory Technician recorded the highest attrition among job roles.
- Single employees showed comparatively higher attrition than married and divorced employees.
- Employees who travelled rarely recorded higher attrition than other travel categories.
- Employees with lower monthly income and fewer total working years showed comparatively higher attrition.
- Younger employees and employees living farther from the workplace showed comparatively higher attrition.

---

### 4. Correlation Analysis

A correlation heatmap was generated to identify relationships among numerical variables.

**Observation**

- Experience-related variables showed strong positive correlations.
- Most other numerical variables exhibited weak to moderate correlations.
- No unexpected or abnormal relationships were observed.

---

### 5. Outlier Analysis

Box plots were used to identify potential outliers in numerical variables.

**Observation**

- Significant outliers were observed in Monthly Income and Total Working Years.
- These outliers represent employees with exceptionally high salaries or extensive work experience and were considered valid observations.
- No significant outliers were observed in Age or Distance From Home.

---

## Summary

The exploratory data analysis identified many factors that are associated with employee attrition. Employees working overtime, employees with lower income, fewer years of work experience, and younger employees showed comparatively higher attrition. Research & Development was the largest department and also recorded the highest attrition count. Correlation analysis highlighted strong relationships among experience-related variables, while outlier analysis confirmed the presence of valid high-value observations in salary and experience. These findings provide the base for KPI analysis, Tableau dashboard development, and business recommendations.