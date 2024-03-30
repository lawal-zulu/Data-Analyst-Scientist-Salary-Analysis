# Data Analyst & Scientist Salary Analysis and Estimator
![](Home.jpg)

# INTRODUCTION
This is a data analysis project looking to provide insight on the salary of data analyst and scientists in the US, UK, Canada, China, Australia and to also get a glimpse into what it can be like to know the expected average salary for a Data analyst or scientist role based on experience level, education and even country.  
_Note: This a dummy data set for me to use to showcase my skills and capabilities._
# TOOLS USED
- SQL – Data cleaning and Analysis,
- Power BI – Creation of Report and Visualization 

# SKILLS DEMONSTRATED
- Use of CASE STATEMENTS and CTE’s in SQL,
- The following power bi features were implemented as well; buttons, page navigation, quick measures, filters.

# DATA SOURCING
I came across this custom or hypothetical dataset of salaries of different professionals including data analyst and scientists on Kaggle which I found really interesting and when I got an idea of what I could create with the data set I downloaded the CSV file. 
## The data contains just one sheet with 9 columns and 6703 rows.
![](Data_sourcing.PNG)

# DATA CLEANING AND TRANSFORMATION
 The data was efficiently cleaned and made more usable using Microsoft SQL Server. Some of the transformation and cleaning ai effected are as follow;
1. Filtering out my data for only data scientists and analyst roles
  ```sql
select Job_Title,count(*) from Salary
select * from Salary
where Job_Title like '%Data Scientist' or Job_Title like '%Data Analyst'
```
2. Created a category for experience level based on years of experience
   
4. Corrected spellings in job title and education columns
5. Created a new column “Age group” for analytical and visualization purposes
6. Simplified Job title column to just Data analyst and Data scientists for analytical and visualization purposes



