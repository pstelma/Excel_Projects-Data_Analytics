# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data comes from an Excel course (Shoutout to Luke Barousse). The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [project_1_dashboard.xlsx](project_1_dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset was made available via Luke Barousse's Excel course.
It includes detailed information on:

-  Job titles
-  Salaries
-  Locations
-  Skills

## Dashboard Build

###  📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img width="700" height="460" alt="image" src="https://github.com/user-attachments/assets/0f8f1221-dd80-44e6-bca3-a667484f339d" />


- Excel Features: Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- Design Choice: Horizontal bar chart for visual comparison of median salaries.
- Data Organization: Sorted job titles by descending salary for improved readability.
- Insights Gained: This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

<img width="700" height="460" alt="image" src="https://github.com/user-attachments/assets/7c71f339-2bc1-4efa-83ba-1e35b17076f8" />



- Excel Features: Utilized Excel's map chart feature to plot median salaries globally.
- Design Choice: Color-coded map to visually differentiate salary levels across regions.
- Data Representation: Plotted median salary for each country with available data.
- Visual Enhancement: Improved readability and immediate understanding of geographic salary trends.
- Insights Gained: Enables quick grasp of global salary disparities and highlights high/low salary regions.

###   Formulas and Functions

####  Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- Multi-Criteria Filtering: Checks job title, country, schedule type, and excludes blank salaries.
- Array Formula: Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- Tailored Insights: Provides specific salary information for job titles, regions, and schedule types.
- Formula Purpose: This formula populates the table below, returning the median salary based on job title, country, and type specified.

 Background Table

<img width="524" height="587" alt="image" src="https://github.com/user-attachments/assets/898a48c2-c2bc-4d3d-8d6c-4f3655ee7bdf" />


 Dashboard Implementation

<img width="524" height="587" alt="image" src="https://github.com/user-attachments/assets/a3c90990-43ef-415f-871f-965eca7c7cc0" />


####  Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- Unique List Generation: This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- Formula Purpose: This formula populates the table below, which gives us a list of unique job schedule types.

 Background Table

<img width="411" height="187" alt="image" src="https://github.com/user-attachments/assets/92d266b0-3f91-4424-9f0b-3b0fce5b7f8c" />




 Dashboard Implementation:

<img width="592" height="661" alt="image" src="https://github.com/user-attachments/assets/575867d9-2a95-4475-aaa3-050a6e1ca149" />


###   Data Validation

####  Filtered List

- Enhanced Data Validation: Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    -  Overall usability of the dashboard is enhanced



## Conclusion

The dashboard showcases insights into salary trends across various data-related job titles. It dashboard allows users to make informed decisions about their career paths by exploring the functionalities to understand how location and job type influence salaries. 
