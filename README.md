# HR Data Integration & Analytics | Talend ETL Pipeline

## Project Overview

This project focuses on designing and implementing an end-to-end **ETL (Extract, Transform, Load) pipeline** for Human Resources data using **Talend Open Studio, SQL, MySQL, and Power BI**.

The objective is to transform raw employee data into structured information that supports HR analytics and decision-making.

The project uses the **IBM HR Analytics Employee Attrition & Performance Dataset** to analyze employee attrition, job satisfaction, workforce distribution, and HR performance indicators.

The solution covers data extraction, cleaning, transformation, integration, data warehouse design, and visualization.

## Objectives

- Design and automate ETL pipelines for HR data.
- Extract employee data from CSV files.
- Clean and validate employee records.
- Handle missing values, duplicates, and inconsistent data.
- Apply HR business rules using Talend tMap.
- Design a relational data warehouse using MySQL.
- Automate data loading into MySQL.
- Develop Power BI dashboards for HR analytics.
- Analyze employee attrition and workforce trends.
- Support data-driven HR decision-making.

## Technologies

| Technology | Purpose |
|------------|---------|
| Talend Open Studio | ETL development and data integration |
| SQL | Data querying and transformation |
| MySQL / MariaDB | Data warehouse and database management |
| Java | Talend job execution |
| Power BI | HR dashboards and data visualization |
| Git & GitHub | Version control and documentation |

## Dataset

**Dataset:** IBM HR Analytics Employee Attrition & Performance

**File:** `WA_Fn-UseC_-HR-Employee-Attrition.csv`

The dataset contains employee information related to demographics, job characteristics, compensation, satisfaction, and attrition.

### Main Attributes

| Attribute | Description |
|-----------|-------------|
| EmployeeNumber | Employee identifier |
| Age | Employee age |
| Department | Employee department |
| JobRole | Employee job position |
| MonthlyIncome | Monthly salary |
| JobSatisfaction | Job satisfaction score |
| WorkLifeBalance | Work-life balance score |
| OverTime | Overtime status |
| YearsAtCompany | Employee tenure |
| TotalWorkingYears | Total professional experience |
| Attrition | Employee attrition status |
| PerformanceRating | Employee performance rating |

## ETL Pipeline Development

### 1. Data Extraction

Extract HR data from CSV files using Talend.

Planned operations:

- Import the HR dataset.
- Configure the input schema.
- Verify column names and data types.
- Inspect source records.
- Prepare data for transformation.

**Talend Components:**
- tFileInputDelimited
- tLogRow

### 2. Data Cleaning and Validation

Implement data quality rules to improve the reliability of HR information.

Planned operations:

- Detect missing values.
- Identify duplicate employee records.
- Validate employee identifiers.
- Check salary and age values.
- Standardize categorical attributes.
- Verify data types.

**Talend Components:**
- tMap
- tFilterRow
- tUniqRow

### 3. Data Transformation

Apply business rules using Talend tMap.

#### Employee Age Classification

```text
IF Age < 30
    THEN "Young"
ELSE IF Age < 45
    THEN "Mid-Career"
ELSE
    "Senior"
```

#### Employee Income Classification

Example business rule:

```text
IF MonthlyIncome < 3000
    THEN "Low Income"
ELSE IF MonthlyIncome < 8000
    THEN "Medium Income"
ELSE
    "High Income"
```

#### Employee Tenure Classification

```text
IF YearsAtCompany < 3
    THEN "New Employee"
ELSE IF YearsAtCompany < 10
    THEN "Experienced Employee"
ELSE
    "Long-Term Employee"
```

These classification thresholds are initial business rules and can be adjusted during data analysis.

### 4. Data Warehouse Design

Design a dimensional data model to support HR analytics.

#### Proposed Star Schema

**Fact Table: Fact_HR**

| Column | Description |
|--------|-------------|
| EmployeeKey | Employee reference |
| DepartmentKey | Department reference |
| JobKey | Job reference |
| AttritionFlag | Employee attrition indicator |
| MonthlyIncome | Employee monthly income |
| JobSatisfaction | Job satisfaction score |
| YearsAtCompany | Employee tenure |

**Dimension Tables:**

- Dim_Employee
- Dim_Department
- Dim_Job

The proposed schema will be refined during the data modeling phase.

### 5. Data Loading

Load transformed HR data into MySQL.

Planned operations:

- Create the data warehouse tables.
- Configure MySQL connections.
- Map source fields to target columns.
- Load dimension tables.
- Load the fact table.
- Validate inserted records.

**Talend Components:**
- tDBConnection
- tDBOutput
- tDBCommit

## ETL Architecture

```text
          IBM HR Analytics Dataset
                    |
                    v
              CSV Data Source
                    |
                    v
             Talend Open Studio
                    |
                    v
              Data Extraction
           (tFileInputDelimited)
                    |
                    v
          Data Quality Validation
        (tFilterRow / tUniqRow)
                    |
                    v
           Data Transformation
                  (tMap)
                    |
                    v
              Data Loading
               (tDBOutput)
                    |
                    v
             MySQL Database
                    |
                    v
             HR Data Warehouse
                    |
                    v
                 Power BI
                    |
                    v
              HR Dashboards
```

## HR Analytics & KPIs

The Power BI dashboards will focus on the following indicators.

| KPI | Description |
|-----|-------------|
| Total Employees | Total number of employee records |
| Attrition Rate | Percentage of employees who left |
| Average Monthly Income | Average employee salary |
| Average Job Satisfaction | Mean employee satisfaction score |
| Overtime Rate | Percentage of employees working overtime |
| Department Distribution | Employees by department |
| Average Employee Tenure | Average years at the company |
| Attrition by Department | Employee attrition across departments |
| Attrition by Job Role | Employee attrition across job positions |
| Attrition by Age Group | Employee attrition by age category |

### Attrition Rate Formula

```text
Attrition Rate (%) =
(Number of Employees with Attrition = Yes
 / Total Number of Employees) * 100
```

## Project Structure

```text
hr-analytics-talend-etl/
|
|-- jobs/
|   |-- data_extraction/
|   |-- data_cleaning/
|   |-- data_transformation/
|   |-- data_loading/
|
|-- datasets/
|   |-- raw/
|   |-- processed/
|
|-- sql/
|   |-- create_database.sql
|   |-- create_dimensions.sql
|   |-- create_fact_table.sql
|   |-- validation_queries.sql
|
|-- powerbi/
|   |-- hr_analytics_dashboard.pbix
|
|-- screenshots/
|   |-- talend-workflow.png
|   |-- tmap-transformation.png
|   |-- mysql-results.png
|   |-- powerbi-dashboard.png
|
|-- docs/
|   |-- etl-architecture.png
|   |-- data-warehouse-schema.png
|
|-- README.md
|-- .gitignore
|-- LICENSE
```

This structure represents the target organization of the repository. Files will be added as development progresses.

## Project Status

**Status: In Progress**

### Development Roadmap

- [ ] Dataset exploration and analysis
- [ ] Data quality assessment
- [ ] ETL extraction pipeline
- [ ] Data cleaning and validation
- [ ] Business rule implementation using tMap
- [ ] MySQL data warehouse design
- [ ] Data integration and loading
- [ ] ETL testing and validation
- [ ] Power BI dashboard development
- [ ] Project documentation

## Screenshots

Screenshots will be added as the project progresses.

### Talend ETL Workflow

<!-- Add Talend workflow screenshot here -->

### Data Transformation Using tMap

<!-- Add tMap transformation screenshot here -->

### MySQL Data Warehouse

<!-- Add MySQL database screenshot here -->

### Power BI HR Dashboard

<!-- Add Power BI dashboard screenshot here -->

## Expected Results

- Automated ETL pipeline for HR data.
- Improved data consistency through validation rules.
- Structured MySQL data warehouse.
- Integrated employee data for analytics.
- HR dashboards displaying workforce indicators.
- Analysis of employee attrition and job satisfaction.

## Future Improvements

- Implement automated data quality monitoring.
- Add ETL error handling and logging.
- Introduce pipeline scheduling.
- Improve ETL performance.
- Integrate additional HR data sources.
- Explore machine learning for employee attrition prediction.

## Author

**Ons Elfekih**

Business Intelligence Engineering Student

GitHub: [OnsElfekih](https://github.com/OnsElfekih)
