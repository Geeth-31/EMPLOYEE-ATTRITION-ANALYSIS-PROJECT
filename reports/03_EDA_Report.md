# Exploratory Data Analysis (EDA) Report

## Objective

The objective of exploratory data analysis (EDA) is to understand the cleaned IBM HR Employee Attrition dataset by analyzing the distribution of all variables and their relationship with employee's attrition. 


## Dataset Overview

I performed the exploratory data analysis on the cleaned dataset that contains:

- Number of Records: **1470**
- Number of Features: **31**

This analysis includes univariate analysis, bivariate analysis, correlation analysis and outlier analysis.

---

## Exploratory Data Analysis

### 1. Target Variable Analysis

I first analyzed the distribution of the target variable (Attrition) to understand employee retention.


__Observation__

- Most of the employees were retained by company.
- Around **83.88%** of employees stayed, while **16.12%** left the organization.
- As the dataset is imbalanced, attrition-related comparisons were explained carefully during the analysis.


### 2. Univariate Analysis

I analyzed each variable individually to understand its distribution 

The following important variables were analyzed individually:

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

__Observations__

- i have observed that Most of the employees belongs to the Research & Development department.
- The most common job role in dataset was Sales Executive.
- Many employees didn't work overtime.
- Many employee travelled under Travel_Rarely category.
- Employee age was concentrated mostly in between 30 and 40 years.
- Monthly Income and Total Working Years showed right-skewed distributions because only a small number of employees had very high salaries or long work experience.


### 3. Bivariate Analysis

I compared employee attrition with all other variables to know which variales were associated with employees leaving the company.

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

__Observations__

- I have found that Employees working overtime shows comparitively higher attrition than employees who did not work overtime.
- Research & Development recorded the highest attrition count because it also had the largest number of employees.
- Among all job roles, Laboratory Technicians has highest attrition.
- The employees who are Single showed comparatively higher attrition than married and divorced employees.
- Employees with lower monthly income and fewer years of work experience showed comparatively higher attrition.
- Employees who are Younger showed higher attrition than older employees.


### 4. Correlation Analysis

I generated a  correlation heatmap to identify the relationships among all the numerical variables present in the dataset.

- I have observed that columns like Total Working Years, Job Level, Monthly Income, and Years at Company have shown positive correlations because employees with more experience generally occupied higher job levels and earned higher salaries. 
- Job Level and Monthly Income specifically showed the strongest correlation on the heatmap around **0.95** with Total Working Years vs Job Level and Total Working Years vs Monthly Income both around **0.77-0.78**.
- Most of the other numerical variables showed weak to moderate correlations.
- There is no unusual relationships observed among the numerical variables.

### 5. Outlier Analysis

I used Box plots to identify possible outliers in numerical variables.

- I have observed that there are Significant outliers in Monthly Income and Total Working Years.
- No significant outliers were observed in Age or Distance From Home.

---

## Summary

The EDA helped me in understanding the attrition pattern and variables that affect it. Overtime, monthly income, work experience, job role, and age all showed some relation with attrition, overtime being the strongest one from what i observed. The analysis also confirmed me that numerical data is  fine to use as it is while the categorical variables provided useful information for dashboard development.

