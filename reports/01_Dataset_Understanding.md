# 1\. Project Background

Employee Attrition is one of the important challenges faced by Organizations. Losing experienced employees increases recruitment costs, reduces productivity and risk of losing organizational knowledge.

Organizations collect HR data to understand employee demographics, job characteristics, compensation, satisfaction, and career progression. Analyzing these factors helps HR departments to identify patterns associated with employee attrition and supports evidence-based retention strategies.

This project analyzes employee data using Python for data analysis and Tableau for visualization to uncover insights related to employee attrition.



# 2\. Business Problem

High employee attrition negatively affects business performance by increasing hiring costs, reducing productivity, disrupting team stability, and lowering employee morale.

The organization needs to understand which employee characteristics and workplace factors are associated with attrition so that HR managers can make informed decisions to improve employee retention.



# 3\. Project Objective

The primary objective of this project is to analyze employee attrition using historical HR data and identify the major factors associated with employees leaving the organization.

The project aims to:

* Understand the employee dataset.
* Perform data cleaning and validation.
* Conduct exploratory data analysis (EDA).
* Identify key HR metrics.
* Build an interactive Tableau dashboard.
* Generate actionable business insights.
* Recommend evidence-based employee retention strategies.



# 4\. Dataset Overview

|Attribute|Value|
|-|-|
|Dataset Name|IBM HR Employee Attrition|
|Domain|Human Resources|
|Number of Records|1470|
|Number of Features|35|
|Target Variable|Attrition|
|Analysis Tools|Python, Tableau|



# 5\. Dataset Summary

The dataset contains demographic information, job-related attributes, compensation details, employee satisfaction metrics, performance indicators, and career history. 





These variables provide a comprehensive view of employee characteristics that may be associated with employee attrition.

# 6. Enhanced Data Dictionary

## 6.1 Target Variable

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| Attrition | Categorical (Yes/No) | Target Variable | Indicates whether an employee has left the organization. This is the primary outcome that the company wants to understand and reduce. | High | This is the dependent (target) variable. All analyses in this project aim to identify the factors associated with employee attrition. |

### Why is Attrition the Target Variable?

Attrition is the primary business problem that the organization wants to solve. Every other feature in the dataset is analyzed to understand whether it has any relationship with employees leaving the company.

---

## 6.2 Demographic Variables

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| Age | Numerical | Demographics | Represents the employee's age, which may influence career stage, work priorities, and likelihood of leaving the organization. | High | Useful for analyzing attrition across different age groups. |
| Gender | Categorical | Demographics | Indicates the employee's gender. It can be analyzed to check whether attrition patterns differ across genders. | Medium | Analyze objectively. Do not assume gender causes attrition without evidence. |
| MaritalStatus | Categorical | Demographics | Indicates whether the employee is Single, Married, or Divorced. Family responsibilities may influence retention decisions. | High | Frequently analyzed in HR analytics because personal responsibilities can affect job decisions. |
| Education | Ordinal (1–5) | Demographics | Represents the employee's highest education level. Higher education may influence career expectations and promotion opportunities. | Medium | Treat as an ordinal variable because the levels have a natural order. |
| EducationField | Categorical | Demographics | Represents the employee's field of study (e.g., Life Sciences, Medical, Marketing). Different educational backgrounds may be associated with different job roles and career paths. | Medium | Useful for comparing attrition among educational disciplines. |
| DistanceFromHome | Numerical | Demographics | Represents the employee's commuting distance between home and workplace. Long commuting distances may reduce work-life balance and increase attrition risk. | High | Strong candidate predictor because commuting burden often influences employee satisfaction. |
| Over18 | Categorical (Y/N) | Demographics | Indicates whether the employee is over 18 years of age. | Low | Expected to contain only one value ("Y"). If confirmed during data cleaning, it will be removed because it provides no analytical value. |

---

## Key Takeaways

- Attrition is the target variable for the entire project.
- Demographic variables help understand whether employee background characteristics are associated with attrition.
- Importance ratings are based on business knowledge and will be validated during Exploratory Data Analysis (EDA).
- Variables such as Over18 may later be removed if they contain only a single unique value.


## 6.3 Job Role & Organizational Structure

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| Department | Categorical | Organizational Structure | Represents the business unit where the employee works (e.g., Research & Development, Sales, Human Resources). Different departments may have different work environments, responsibilities, and attrition rates. | High | Useful for comparing attrition across departments and identifying departments requiring retention strategies. |
| JobRole | Categorical | Organizational Structure | Represents the employee's specific job designation within the organization. Different job roles may experience different workloads, career growth opportunities, and satisfaction levels. | High | One of the most important variables for understanding which job roles experience higher employee turnover. |
| JobLevel | Ordinal (1–5) | Organizational Structure | Indicates the employee's hierarchical level within the organization. Higher job levels generally correspond to greater responsibility and experience. | High | Useful for analyzing attrition across different seniority levels. Treat as an ordinal variable because the levels have a natural order. |
| EmployeeNumber | Identifier | Employee Identifier | Unique identification number assigned to each employee. Used only to uniquely identify records. | Low | This column has no business meaning for analysis and should be excluded from statistical analysis and visualizations. |
| BusinessTravel | Categorical | Work Characteristics | Indicates how frequently the employee travels for business (Non-Travel, Travel Rarely, Travel Frequently). Frequent travel may affect work-life balance and job satisfaction. | High | Important predictor because business travel can influence stress levels and employee retention. |
| EmployeeCount | Numerical (Constant) | Administrative | Represents the employee count recorded in the dataset. | Low | Expected to contain only one unique value for every record. If confirmed during data cleaning, this column will be removed because it provides no analytical value. |

---

### Key Takeaways

- Department and JobRole help identify which parts of the organization experience the highest employee attrition.
- JobLevel provides insight into whether junior or senior employees are more likely to leave.
- BusinessTravel may influence employee satisfaction due to travel demands.
- EmployeeNumber is only an identifier and should never be used as a predictive feature.
- EmployeeCount is expected to be a constant column and will likely be removed during data cleaning.


