# Data Cleaning Report

## Objective

The main objective of this data cleaning process is to inspect the IBM_HR_Employee_Attrition.csv dataset to classify the variables and find out the data quality issues. This helps in making a cleaner dataset for exploratory data analysis (EDA), KPI analysis, and dashboard development.


## Dataset Overview

The dataset that was used in this project contains information about each employee's personal details and their job characteristics.Also,it includes salary, work experience and attrition status,satisfaction levels,etc..

__Dataset Summary__

- Number of Records: **1470**
- Number of Features (Original): **35**
- Number of Features (After Cleaning): **31**

---

## Data Cleaning Process

### 1. Loaded the dataset

The dataset was imported into a Pandas DataFrame using the `read_csv()` function.I confirmed that the dataset was loaded successfully.


### 2. Initial Data Checking

The dataset structure was studied using:

- Shape of the dataset
- Data types of all columns
- Statistical information of all numerical variables
- Summary of all the categorical variables

This gave me a clear picture about the characteristics and quality of the dataset before i started cleaning the dataset.


### 3. Checked for Missing values 

The dataset was checked for missing values using the `isnull()` function.

__Observation__

- I did not find missing values in any column of the dataset.


### 4. Checked for Duplicate records 

The dataset was checked for Duplicate records using the `duplicated()` function.

__Observation__

- No duplicate records were found in the dataset.


### 5. Constant Column Identification

Columns that contain only a single unique value are identified first because they do not contribute any meaningful information to the analysis.

The columns that contains constant values are identified here :

- EmployeeCount
- StandardHours
- Over18
- EmployeeNumber

Though EmployeeNumber column have different constant values, they don't actually seeming to contribute to the attrition (target variable) analysis ,so i dropped it.

so, I removed these four columns from the dataset leaving only 31 features available in dataset.


### 6. Data Type Classification

The remaining variables were then classified to three categories:

- Numerical Variables
- Categorical Variables
- Ordinal Variables

There are some columns like Education, Joblevel,etc.. which also have numeric values but they are not considered to be Numerical Variables as they give an ordering or rank categories. 

This classification helped me in choosing suitable analysis and visualization techniques during EDA. 


### 7. Saved the Cleaned Dataset 

After completing the cleaning, the cleaned dataset containing **31 features** was exported and saved as `IBM_HR_Employee_Attrition_Cleaned.csv` for further analysis.

---

## Summary

-The initial data check showed that the dataset is of good quality with no missing values or duplicate records.So, cleaning was mainly focused on validating the dataset before analysis.

-Four constant columns were removed from dataset as they did not provide any useful analytical information. The remaining variables were classified by their data types, the cleaned dataset was now fully prepared for EDA, KPI analysis, and Tableau dashboard development.

