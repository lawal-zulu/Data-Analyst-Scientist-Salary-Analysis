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
--This SQL code performs the following actions: Creates a temporary result set named "filter" containing rows from the "salary" table where the "Job_Title" column contains "Data Scientist" or "Data Analyst".
select * from Salary
where Job_Title like '%Data Scientist' or Job_Title like '%Data Analyst'
```
2. Created a category for experience level based on years of experience
   ```sql
   with filter as (select * from salary WHERE Job_Title like '%Data Scientist' or Job_Title like '%Data Analyst')
   select job_title,years_of_experience,
   case when years_of_experience <= 2 then 'Entry level'
     when years_of_experience <= 5 then 'Mid level'
   else 'Senior level'
   end as experience_level
   from filter;

   alter table salary
   add experience_level nvarchar(50);

   update salary
   set experience_level = case when years_of_experience <= 2 then 'entry level'
     when years_of_experience <= 5 then 'Mid level'
   else 'Senior level';
```   
3. Corrected spellings in the education column
   ```sql
   with filter as (select * from salary
   WHERE Job_Title like '%Data Scientist' or Job_Title like '%Data Analyst')
   select education,
   case when education like '%Bachelor%' then 'Bachelor''s Degree'
     when education like '%Master%' then 'Master''s Degree'
	  else education
   end
   from filter;

   update Salary
   set Education= case when education like '%Bachelor%' then 'Bachelor''s Degree'
     when education like '%Master%' then 'Master''s Degree'
   else education
   end;
```
5. Created a new column “Age group” for analytical and visualization purposes
6. Simplified Job title column to just Data analyst and Data scientists for analytical and visualization purposes



