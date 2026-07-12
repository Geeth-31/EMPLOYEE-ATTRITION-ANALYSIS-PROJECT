# Data Cleaning Report

## Objective

The objective of this data cleaning process is to inspect the IBM HR Employee Attrition dataset to classify the variables and identify the issues in quality of data .This helps in making of a clean dataset for exploratory data analysis (EDA), KPI analysis, and dashboard development.

---

## Dataset Overview

The dataset contains information about each employee such as their perosnal details, job characteristics, salary and work experience, satisfaction levels, attrition status.

**Dataset Summary**

- Number of Records: **1470**
- Number of Features (Original): **35**
- Number of Features (After Cleaning): **31**

---

## Data Cleaning Process

### 1. Dataset Loading

The dataset was imported into a Pandas DataFrame using the `read_csv()` function.I confirmed the Initial verification that the dataset was loaded successfully.

---

### 2. Initial Data Inspection

The dataset structure was examined using:

- Shape of the dataset
- Data types of all columns
- Statistical information of numerical variables
- Summary of categorical variables

This helped me in understanding the overall quality and characteristics of the dataset before cleaning.

---

### 3. Missing Value Analysis

The dataset was checked for missing values using the `isnull()` function.

**Observation**

- I did not find missing values in any column of the dataset.

---

### 4. Duplicate Record Analysis

The dataset was checked for Duplicate records using the `duplicated()` function.

**Observation**

- I did not find duplicate records  in any column of the dataset.

---

### 5. Constant Column Identification

Columns that contains only a single unique value were identified because they do not contribute any meaningful information to the analysis.

The following columns were identified as constant:

- EmployeeCount
- StandardHours
- Over18
- EmployeeNumber

These columns were removed from the dataset.

---

### 6. Data Type Classification

The remaining variables were classified into three categories:

- Numerical Variables
- Categorical Variables
- Ordinal Variables

This classification helped me in selecting appropriate analysis and visualization techniques during exploratory data analysis.

---

### 7. Cleaned Dataset Export

After completing all cleaning steps, the cleaned dataset containing **31 features** was exported and saved in the **data/cleaned** directory for further analysis.

---

## Summary

The data cleaning process confirmed that the dataset was of good quality, with no missing values and no duplicate records. Four constant columns were removed as they did not provide useful analytical information. The remaining variables were classified according to their data types, and the cleaned dataset was successfully prepared for exploratory data analysis, KPI analysis, and Tableau dashboard development.