# End-to-End-HR-Analytics
End-to-end HR analytics project using Snowflake, S3, and Power BI reports


This project focuses on HR data analysis by integrating Snowflake (cloud data warehouse) with Power BI to generate interactive dashboards and insights. The objective is to help HR teams understand workforce trends and support data-driven decisions.

##  Overview

- Data is stored in Snowflake and loaded via S3 stages.
- Power BI connected directly to Snowflake
- The report contains 4 interactive pages covering Overview, Demographics, Performance Tracker, Attrition
- Actionable recommendations are provided based on data insights.

##  Technologies Used

- **Snowflake** – cloud data warehousing, dynamic date table creation
- **Amazon S3** – external stage for file storage
- **Power BI** – business intelligence and visualization
  

## Project Setup

1. **Snowflake Setup**
   - Created `POWERBI_HRANALYTICS` database and `PBI_Data` schema.
   - Created tables: `Employee`, `PerformanceRating`, `EducationLevel`, `RatingLevel`, `SatisfiedLevel`, `DimDate`.
   - Loaded CSV data into Snowflake using `COPY INTO` and external S3 stage.
   - Built a `DimDate` table for time intelligence in reports.

2. **Power BI Setup**
   - Connected to Snowflake using native Power BI connector.
   - Imported required tables into the model.
   - Created measures and relationships between tables.

##  **Report Pages**

1. **Overview**  
   Active employees count, inactive employees count, attrition rate, department distribution, and hiring trends.

2. **Demographics**  
   Breakdown of Employees by age, marital status, gender, and ethnicity.

3. **Performance Tracker**  
   Visuals on job satisfaction, work-life balance, and relationship with management.

4. **Attrition**  
   Insights on attrition by tenure, attrition by hiredate, attrition by over time requirement

##  **Recommendations**

Based on the data, the following recommendations are made:

- Address high attrition in departments with high overtime and travel frequency.
- Improve work-life balance and relationship satisfaction for lower-performing teams.
- Increase training opportunities for employees with low self-ratings.
- Focus on departments with low job satisfaction for retention strategies.
- Enhance training programs and continuous learning programs to reduce junior employee attrition
  
  
