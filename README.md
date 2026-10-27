# End-to-End HR Analytics | AWS S3, Snowflake & Power BI

### Cloud Data Engineering | SQL | Data Modeling | Business Intelligence

Developed an end-to-end HR analytics solution integrating **Amazon S3, Snowflake, SQL, and Power BI** to transform raw employee data into structured, actionable business insights.

The project covers cloud data ingestion, data warehousing, dimensional modeling, and interactive reporting across **1,470 employee records**, helping explore workforce trends, employee performance, and attrition.

## 📊 Project Dashboard

**[View Power BI Dashboard (PDF)](https://github.com/ThanmayiKarpurapu/End-to-End-HR-Analytics/blob/main/HRANALYTICS_SNOWFLAKE.pdf)**

**[View Power BI Project File](https://github.com/ThanmayiKarpurapu/End-to-End-HR-Analytics/blob/main/HRANALYTICS_SNOWFLAKE.pbix)**

## 🎯 Business Objective

Build a centralized analytics solution that enables HR teams to:

- Monitor workforce KPIs and hiring trends.
- Analyze employee demographics and performance.
- Identify potential factors associated with employee attrition.
- Support workforce planning and retention strategies.
- Improve access to structured, reliable HR reporting.

## 🛠️ Technologies & Tools

| Component | Technology |
|---|---|
| Cloud Storage | Amazon S3 |
| Data Warehouse | Snowflake |
| Data Ingestion | Storage Integration, External Stage, `COPY INTO` |
| Data Transformation | SQL |
| Data Modeling | Star Schema, Fact & Dimension Tables, DimDate |
| Business Intelligence | Microsoft Power BI |
| Reporting | KPI Dashboards, Trend Analysis, Interactive Visualizations |

## 🏗️ Architecture & Data Pipeline

**Amazon S3 → Snowflake → Data Modeling → Power BI**

1. **Data Storage:** Uploaded raw HR datasets to Amazon S3.
2. **Secure Integration:** Configured Snowflake storage integration using an AWS IAM role.
3. **Data Ingestion:** Created an external stage and loaded CSV datasets using Snowflake's `COPY INTO` command.
4. **Data Preparation:** Organized employee, performance, and lookup data into structured Snowflake tables.
5. **Dimensional Modeling:** Created fact and dimension relationships, including a dynamically generated `DimDate` table.
6. **Business Intelligence:** Connected Power BI to Snowflake, built relationships and measures, and developed interactive dashboards.

## 🗄️ Database Design

The Snowflake data warehouse contains the following tables:

| Table | Description |
|---|---|
| `Employee` | Employee attributes, department information, and HR metrics |
| `PerformanceRating` | Employee performance reviews and satisfaction scores |
| `EducationLevel` | Education-level lookup data |
| `RatingLevel` | Performance rating categories |
| `SatisfiedLevel` | Satisfaction-level lookup data |
| `DimDate` | SQL-generated date dimension for time-based reporting |

The data model supports analysis across employee demographics, performance, hiring trends, and attrition.

## ⚙️ Data Ingestion & ETL

Implemented a cloud-based data ingestion workflow using Snowflake and Amazon S3.

**Key Implementation Steps:**
- Configured a Snowflake `STORAGE INTEGRATION` with an AWS IAM role.
- Created an external stage to access HR datasets stored in Amazon S3.
- Loaded CSV files into Snowflake tables using `COPY INTO`.
- Created a dynamic date dimension to support time-based analysis.
- Prepared structured datasets for Power BI reporting.

**Example Snowflake SQL:**

```sql
COPY INTO Employee
FROM @pbi_stage2/Employee.csv
FILE_FORMAT = (
    TYPE = CSV
    FIELD_DELIMITER = ','
    SKIP_HEADER = 1
)
ON_ERROR = 'continue';
```

The `ON_ERROR = 'continue'` option allows loading to proceed when problematic records are encountered. Rejected records should be reviewed using Snowflake's load validation and history capabilities to ensure data quality.

## 📈 Power BI Data Modeling & Reporting

Connected Power BI to Snowflake using the native connector, imported the required tables, established relationships, and created analytical measures.

Developed four report pages:

### 1. Workforce Overview

Provides an executive-level view of employee headcount and workforce trends.

**Key Metrics:**
- Total Employees: **1,470**
- Active Employees: **1,233**
- Inactive Employees: **237**
- Attrition Rate: **16.1%**

**Visualizations:**
- Employee hiring trends
- Active employees by department
- Workforce distribution by job role

### 2. Employee Demographics

Analyzes workforce composition across demographic categories.

**Key Analyses:**
- Employee distribution by age group
- Gender and marital status
- Ethnicity and average salary
- Workforce demographic comparisons

### 3. Performance Tracker

Tracks individual employee performance and satisfaction metrics over time.

**Key Analyses:**
- Job satisfaction
- Environment satisfaction
- Manager ratings
- Self-ratings
- Work-life balance

### 4. Employee Attrition Analysis

Explores workforce attrition patterns to identify potential retention challenges.

**Key Analyses:**
- Attrition by department and job role
- Attrition by overtime requirement
- Attrition by business travel frequency
- Attrition by employee tenure
- Attrition trends by hiring date

## 💡 Business Insights & Recommendations

### 1. Workforce Attrition

The dataset contains **237 inactive employees out of 1,470 total employees**, representing an overall attrition rate of approximately **16.1%**.

**Recommendation:** Monitor attrition trends across departments and job roles to identify areas requiring further investigation.

### 2. Overtime & Retention

The attrition dashboard enables comparisons between employees with and without overtime requirements.

**Recommendation:** Investigate whether overtime-intensive roles experience higher attrition and evaluate potential workload or staffing adjustments.

### 3. Business Travel

Employee attrition can be analyzed across different travel-frequency categories.

**Recommendation:** Assess whether frequent travel is associated with retention challenges and consider employee support initiatives where appropriate.

### 4. Employee Tenure

Attrition patterns vary across employee tenure groups.

**Recommendation:** Identify tenure periods associated with elevated attrition and evaluate onboarding, career development, and retention initiatives.

### 5. Employee Performance & Satisfaction

The Performance Tracker provides visibility into satisfaction scores, manager ratings, and work-life balance.

**Recommendation:** Use these indicators to identify areas for further employee engagement and performance analysis.

## 📌 Business Value

This project demonstrates how cloud data engineering and business intelligence can support workforce analytics by:

- Consolidating HR datasets into a structured cloud data warehouse.
- Supporting consistent workforce KPI reporting.
- Enabling interactive analysis of employee performance and attrition.
- Providing a foundation for evidence-based workforce planning.
- Connecting technical data workflows with business decision-making.

## 🔍 Skills Demonstrated

**Data Engineering:** AWS S3, Snowflake, Cloud Data Ingestion, SQL, ETL

**Data Modeling:** Relational Tables, Dimensional Modeling, Star Schema, Date Dimensions

**Business Intelligence & Reporting**: Power BI, DAX Measures, Power Query, Interactive Dashboards, KPI Reporting, Data Visualization, Data-Driven Recommendations

## 📁 Project Files

- **Dashboard PDF:** Four-page HR Analytics report.
- **Snowflake SQL Scripts:** Data ingestion, table creation, and date dimension scripts.
- **Power BI File:** Report and data model, where available.
- **README:** Project architecture, implementation, and business insights.

## 👩‍💻 Author

**Sai Thanmayi Karpurapu**


