# Project 2 Analysis

## Introduction

This project explores the most optimal jobs and skills in the data science market and can help job seekers understand what skills employers request for different data related roles and how different skills relate to monetary compensation.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills equal higher salary?**
2. **What are the salaries for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 sought after skills?**

### Excel Skills Used

The following Excel skills were utilized for the analysis:

-  Pivot Tables
-  Pivot Charts
-  DAX (Data Analysis Expressions)
-  Power Query
-  Power Pivot

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset was available via Luke Barousse's Excel course with the intention of providing a foundation for Excel data analysis.

The dataset includes detailed information on:

-  Job titles
-  Salaries
-  Locations
-  Skills

## 1️⃣ Do more skills equal higher salary?

### skill: Power Query (ETL)

#### Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    -  First one with all the data jobs information.
    -  The second listing the skills for each job ID.

####  Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    -  data_jobs_salary

       <img width="307" height="370" alt="image" src="https://github.com/user-attachments/assets/345cf824-09be-425b-bde7-c82674708348" />



    -  data_job_skills

        <img width="307" height="370" alt="image" src="https://github.com/user-attachments/assets/1e75501b-60fd-4849-8923-1d602d0be4bf" />

####  Load

- Finally, I loaded both transformed queries into the workbook as the foundation for my analysis.
    -  data_jobs_salary

        <img width="1400" height="810" alt="image" src="https://github.com/user-attachments/assets/4e40a8e4-e1d0-4b23-85a5-4aca6fd1b055" />



    -  data_job_skills

        <img width="1400" height="810" alt="image" src="https://github.com/user-attachments/assets/44c8c4e5-5f79-406c-98a6-7dbdd9531fc6" />


###  Analysis

####  Insights

-  There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
-  Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    <img width="695" height="416" alt="image" src="https://github.com/user-attachments/assets/dda01dc1-96a2-43ae-a318-f5c4b9f99471" />


#### Insights

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

###  Skills: PivotTables & DAX

#### Pivot Table

-  I created a PivotTable using the Data Model I created with Power Pivot.
-  I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
-  Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_salary[salary_year_avg]),
        data_jobs_salary[job_country] = "United States")
    ```

####  DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_salary[salary_year_avg])
    ```

###  Analysis

####  Insights

-  Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
-  The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    <img width="700" height="270" alt="image" src="https://github.com/user-attachments/assets/d4148909-4e5f-4585-af60-167e6ea20508" />


#### Insights

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

###  Skill: Power Pivot

####  Power Pivot

-  I created a data model by integrating the `data_jobs_salary` and `data_jobs_skills` tables into one model.
-  Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

####  Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/60e80816-b40b-44cc-ace0-192f7eeaaf8c" />


####  Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    <img width="800" height="650" alt="image" src="https://github.com/user-attachments/assets/b93449fd-b75a-4ef7-80ea-32cdb82cef25" />


### Analysis

#### Insights

-  SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    <img width="700" height="320" alt="image" src="https://github.com/user-attachments/assets/3635a980-1ba6-44d7-a6d2-4ac57d29742e" />


#### Insights

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

###  Skill: Advanced Charts (Pivot Chart)

####  PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    -  Primary Axis: Median Salary (as a Clustered Column)
    -  Secondary Axis: Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

###  Analysis

#### Insights

-  Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
-  Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    <img width="900" height="335" alt="image" src="https://github.com/user-attachments/assets/0016634c-c6eb-4285-82cf-833b3e3c3798" />


### Insights

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As a job seeker, this Excel project provided me with valuable insights about the data science job market. Using a dataset gathered from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies like AWS. 


