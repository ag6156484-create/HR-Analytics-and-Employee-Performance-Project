# HR-Analytics-and-Employee-Performance-Project
Power BI Dashboard analysing employee attrition drivers, workforce demographics, and turnover root causes
 📊 HR Analytics & Employee Performance Dashboard

 📌 Executive Summary
This project presents an interactive Power BI dashboard designed to analyze employee turnover rates, identify key attrition drivers, and provide actionable HR recommendations. By analyzing workforce demographics, job roles, compensation, and satisfaction metrics, this solution helps HR leadership implement targeted retention strategies to reduce costly employee turnover.

 🖼️ Dashboard Preview
 
 1. HR Attrition Overview
    
   
2. Root Cause & Job Role Analysis
   
3.🛠️ Data Cleaning & Transformations (Power Query)
The raw dataset was cleaned and structured using *Power Query Editor* to ensure data integrity and accurate analysis:

* Data Type Formatting: Applied strict data types across numeric (Age, MonthlyIncome,TotalWorkingYears) and categorical attributes.
* Missing & Duplicate Value Handling: Checked and removed duplicate records and handled missing fields.
* Custom Conditional Columns: Created age groups (<25, 25-34, 35-44, 45+) ,tenure buckets,income bucket for granular demographic cohort analysis.
* Data Standardization: Cleaned text entries and mapped binary attrition categories (Yes / No) for accurate DAX aggregation.

 📐 Key DAX Measures
Core KPI calculations built using *Data Analysis Expressions (DAX)* in Power BI:

dax
 1. Total Employees
Total Employees = COUNT('HR_Analytics'[EmployeeID])

 2. Active Employees
Active Employees = 
CALCULATE(
    COUNT('HR_Analytics'[EmployeeID]), 
    'HR_Analytics'[Attrition] = "No"
)

 3. Attrition Count
Attrition Count = 
CALCULATE(
    COUNT('HR_Analytics'[EmployeeID]), 
    'HR_Analytics'[Attrition] = "Yes"
)

// 4. Attrition Rate (%)
Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)


# Key Data Insights

# High-Level Attrition Overview

1 Overall Attrition Rate: 16.12% (237 employees left out of 1,470 total workforce).
2 Department Breakdown: Research & Development accounts for the highest attrition (58.27%), followed by Sales (37.8%) and Human Resources (3.94%).
3 Education Field: Life Sciences and Medical backgrounds show the highest volume of employee departures.
4 Tenure Vulnerability: Mid-Level (38.16%) and Experienced (37.82%) employees combined represent over 75% of overall turnover.

🔍 Root Cause Analysis Findings

1 Primary Driver (Overtime & Low Income): 92.45% of employees who left due to high overtime workload belong to the Low-Income Group.
2 High-Risk Roles: Laboratory Technicians, Research Scientists, and Sales Executives exhibit the highest turnover counts. Sales Representatives show a disproportionately high churn rate (~40%).
3 Demographics: Employees aged 26–35 and Under 25 (primarily Single or Married) show the highest rate of departures due to work-life balance challenges.

💡 Strategic HR Recommendations

1 Overtime Compensation & Workload Balance: Re-evaluate workload distribution for Laboratory Technicians and Research Scientists, ensuring fair overtime compensation or hiring support to reduce burnout.
2 Targeted Retention for Mid-Level Staff: Introduce structured career growth pathways and salary adjustments for employees in the 26–35 age group and 1–3 year tenure bracket.
3 Sales Role Restructuring: Redesign incentive structures and travel demands for Sales Representatives to curb early turnover.
















