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


## 6.4 Compensation & Financial Variables

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| MonthlyIncome | Numerical | Compensation | Represents the employee's monthly salary. Compensation plays an important role in employee satisfaction and retention. | High | One of the most important financial variables for attrition analysis. |
| DailyRate | Numerical | Compensation | Represents an internally assigned daily rate used by the organization. | Medium | The exact business definition is not provided by IBM. Analyze carefully and avoid assuming it is the employee's daily salary. |
| HourlyRate | Numerical | Compensation | Represents an internally assigned hourly rate. | Medium | Do not interpret this as the employee's hourly wage unless supported by documentation. |
| MonthlyRate | Numerical | Compensation | Represents an internal monthly rate maintained by the organization. | Medium | Different from MonthlyIncome. Should not be confused with salary. |
| PercentSalaryHike | Numerical | Compensation | Represents the percentage increase in salary received during the latest performance cycle. | High | Useful for understanding whether salary growth influences employee retention. |
| StockOptionLevel | Ordinal (0–3) | Compensation | Represents the level of company stock options granted to the employee. Higher levels generally indicate greater long-term financial benefits. | High | Employees with higher stock options may have stronger incentives to remain with the company. |

---

### Key Takeaways

- MonthlyIncome is expected to be one of the strongest predictors of employee attrition.
- Salary growth (PercentSalaryHike) may influence employee motivation and long-term retention.
- StockOptionLevel represents long-term financial incentives rather than direct salary.
- DailyRate, HourlyRate, and MonthlyRate are internal organizational metrics and should not automatically be interpreted as employee wages without supporting documentation.


## 6.5 Performance & Behavioral Metrics

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| JobSatisfaction | Ordinal (1–4) | Employee Satisfaction | Represents the employee's overall satisfaction with their job. | High | Lower job satisfaction may be associated with higher attrition. Analyze this relationship using the data before drawing conclusions. |
| EnvironmentSatisfaction | Ordinal (1–4) | Employee Satisfaction | Measures the employee's satisfaction with the workplace environment. | High | A positive work environment can influence employee retention. |
| JobInvolvement | Ordinal (1–4) | Employee Engagement | Indicates how engaged the employee is in their daily work activities. | High | Employees with low job involvement may be more likely to leave the organization. |
| RelationshipSatisfaction | Ordinal (1–4) | Employee Satisfaction | Represents satisfaction with relationships at work, including colleagues and managers. | Medium | Healthy workplace relationships can contribute to employee retention. |
| WorkLifeBalance | Ordinal (1–4) | Employee Well-being | Represents the employee's perception of their work-life balance. | High | Poor work-life balance is frequently studied as a factor influencing attrition. |
| PerformanceRating | Ordinal (3–4) | Performance | Represents the manager's evaluation of employee performance. | Medium | Useful for exploring whether performance ratings differ between employees who stay and those who leave. |

---

### Key Takeaways

- Satisfaction-related variables measure different aspects of the employee experience and should not be treated as interchangeable.
- WorkLifeBalance and JobSatisfaction are commonly investigated in HR analytics because they may influence employee retention.
- PerformanceRating should not automatically be interpreted as a cause of attrition; its relationship with attrition must be verified through analysis.


## 6.6 Tenure & Career History

| Column | Data Type | Category | Business Meaning | Importance | Analyst Notes |
|---------|-----------|----------|------------------|------------|---------------|
| OverTime | Categorical (Yes/No) | Work Pattern | Indicates whether the employee regularly works overtime. | High | Overtime may be associated with increased workload, stress, and reduced work-life balance. Its relationship with attrition will be verified during analysis. |
| TotalWorkingYears | Numerical | Career History | Represents the employee's total years of professional work experience across all organizations. | High | Useful for comparing attrition among employees with different experience levels. |
| YearsAtCompany | Numerical | Organizational Tenure | Represents the number of years the employee has worked in the current organization. | High | Helps determine whether new or long-serving employees are more likely to leave. |
| YearsInCurrentRole | Numerical | Career Progression | Represents the number of years the employee has remained in their current job role. | Medium | Employees who remain in the same role for long periods may have different career expectations and engagement levels. |
| YearsSinceLastPromotion | Numerical | Career Progression | Represents the number of years since the employee last received a promotion. | High | Longer periods without promotion may influence employee motivation and retention. |
| YearsWithCurrManager | Numerical | Management Relationship | Represents the number of years the employee has worked under their current manager. | Medium | Stable manager-employee relationships may influence job satisfaction and retention. |
| NumCompaniesWorked | Numerical | Career History | Represents the total number of companies the employee has worked for before joining the current organization. | Medium | May indicate career stability or frequent job changes. |
| TrainingTimesLastYear | Numerical | Learning & Development | Represents the number of training programs attended during the previous year. | Medium | Useful for analyzing whether employee development opportunities are associated with retention. |
| StandardHours | Numerical (Constant) | Administrative | Represents the organization's standard working hours. | Low | Expected to contain a single constant value for all employees. If confirmed during data cleaning, this column will be removed because it provides no analytical value. |

---

### Key Takeaways

- Career progression variables help understand whether promotion opportunities and role growth are associated with employee retention.
- Overtime is an important work-pattern variable that may influence employee well-being and attrition.
- Training participation provides insight into employee development initiatives.
- StandardHours is expected to contain only one unique value and will likely be removed during data cleaning because it does not contribute meaningful information.