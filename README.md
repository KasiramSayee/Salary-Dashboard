# Excel Salary Dashboard  

<img width= "950" height="640" alt = "1_Salary_Dashboard_Final_Dashboard" src = "https://github.com/user-attachments/assets/2293eea5-7e69-429d-b50d-b069f2ac4397">

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [Salary_Dashboard_Project.xlsx](https://github.com/user-attachments/files/24352864/Salary_Dashboard_Project.xlsx)


### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset provides a foundation for analyzing data using Excel. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart  

<img width="736" height="567" alt="1_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/92808790-0a38-4f72-b40c-b207c5da7434" />

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/4a0b9d6d-0a65-46ba-8bb6-28eb5bae915a)


- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions  

#### 🛠️ Data Cleaning  

Different jobs are said to have either yearly salary or hourly salary. So the "salary_year_avg" and the "salary_hour_avg", these two columns which represent the salary for the jobs has been combined in order to get the overall "salary" column.

salary_hour_avg_adjusted  
`= [@salary_hour_avg]*2080`

salary  
`= IF([@salary_year_avg]<>0, [@salary_year_avg], [@salary_hour_avg_adjusted])`

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (jobs[job_schedule_type]=type)*
    (jobs[salary]<>0),
    jobs[salary]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

<img width="265" height="220" alt="1_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/9da2d8c1-9023-411c-8904-e433a4cd5777" />


📉 Dashboard Implementation

<img width="448" height="614" alt="1_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/4f49af71-2b0e-43af-9794-1ddbb328cee6" />


#### ⏰ Count of Job Schedule Type

```
=FILTER(M2#,NOT(ISNUMBER(SEARCH("and",M2#))))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

<img width="195" height="119" alt="1_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/bbc83b87-5820-4cac-ab03-13ddf1eaca40" />

📉 Dashboard Implementation:

<img width="342" height="512" alt="1_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/f8a83bf4-0750-4558-87b2-a155d60141ca" />

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

<img width="382" height="524" alt = "1_Salary_Dashboard_Data_Validation" src = "https://github.com/user-attachments/assets/d7dc7c9f-d5e4-4beb-9640-77fdb7cacde7">


## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. This dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
