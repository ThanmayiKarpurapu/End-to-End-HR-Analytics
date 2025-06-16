## End-to-End HR Analytics Project   
Cloud-Based HR Data Pipeline using **Snowflake**, **Amazon S3**, and **Power BI**

This project simulates a complete HR analytics pipeline—from raw data in Amazon S3 to dashboards in Power BI—using **cloud-native ETL with Snowflake**. It highlights secure data ingestion, data modeling, and business intelligence for actionable HR insights.


## Project Objective

Help HR teams make informed, data-driven decisions by transforming raw HR data into structured insights through:
- Secure data ingestion
- Cloud data warehousing
- Dimensional modeling
- Real-time dashboarding


## Technologies & Tools

| Layer              | Tool/Technology                                  |
|--------------------|--------------------------------------------------|
| Cloud Storage      | **Amazon S3**                                    |
| Data Warehouse     | **Snowflake**                                    |
| ETL Mechanism      | **External Stage**, **Storage Integration**, `COPY INTO` |
| Data Modeling      | **Star Schema**, **DimDate** generation          |
| BI & Visualization | **Power BI**                                     |


## Architecture Workflow

1. **Raw Data Upload** → Amazon S3  
2. **Secure Integration** → Snowflake IAM Role & Storage Integration  
3. **Staging & Load** → External Stage in Snowflake + `COPY INTO`  
4. **Data Modeling** → Snowflake tables (Fact & Dimension)  
5. **Date Table Creation** → Fully automated `DimDate` SQL script  
6. **Visualization** → Power BI report connected to Snowflake  


## Dataset & Tables

| Table Name          | Description                              |
|---------------------|------------------------------------------|
| `Employee`          | Main employee attributes & HR metrics    |
| `PerformanceRating` | Satisfaction scores & manager reviews    |
| `EducationLevel`    | Education levels (lookup)                |
| `RatingLevel`       | Rating categories (lookup)               |
| `SatisfiedLevel`    | Satisfaction levels (lookup)             |
| `DimDate`           | Dynamic time dimension (for Power BI)    |


## ETL Process in Snowflake

- Configured `STORAGE INTEGRATION` using IAM role
- Created an external stage to securely access files in `s3://myhranalyticsproject`
- Used `COPY INTO` to ingest CSV data into Snowflake tables
- Applied `on_error='continue'` to handle data anomalies gracefully

Example:
```sql
COPY INTO Employee
FROM @pbi_stage2/Employee.csv
FILE_FORMAT = (TYPE=CSV FIELD_DELIMITER=',' SKIP_HEADER=1)
ON_ERROR = 'continue';
```

## **Power BI Setup**
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
  
  
