# Talend ETL & Data Integration

## Project Overview

This project focuses on designing and implementing **ETL (Extract, Transform, Load) pipelines** using **Talend Open Studio, SQL, and MySQL**.

It demonstrates how data can be extracted from multiple sources, transformed according to business rules, and loaded into relational databases for analytics and reporting.

## Objectives

- Automate data integration processes.
- Extract data from CSV files and relational databases.
- Transform and validate data.
- Apply business rules.
- Load processed data into MySQL.
- Prepare datasets for business intelligence analysis.

## Technologies

| Technology | Purpose |
|------------|---------|
| Talend Open Studio | ETL development and orchestration |
| SQL | Data querying and manipulation |
| MySQL / MariaDB | Database management |
| Java | Talend job execution |
| Power BI | Data analysis and visualization |
| Git & GitHub | Version control |

## Implemented ETL Workflows

### 1. Product and Sales Data Processing

Developed an ETL workflow to process product and sales information.

Implemented transformations using **Talend tMap**, including:

- Product classification into Premium and Standard categories.
- Conditional business rules.
- Data mapping and transformation.
- Database loading.

**Business Rule Example:**

```text
IF (TotalAmount / Quantity >= 200)
    THEN ProductCategory = "Premium"
ELSE
    ProductCategory = "Standard"
```

### 2. Multi-Source Data Integration

Developed an ETL pipeline integrating three CSV datasets.

The workflow performs:

- Data extraction from CSV files.
- Dataset joins using tMap.
- Data transformation.
- Data loading into MySQL.

**Output Dataset Structure:**

| Column | Description |
|--------|-------------|
| ProductID | Product identifier |
| CustomerID | Customer identifier |
| Quantity | Quantity sold |
| TotalPrice | Total transaction amount |
| ProductName | Product name |
| Price | Unit price |
| CustomerName | Customer name |
| Country | Customer country |

### 3. Database Integration

Implemented database connections to automate the loading of transformed data into MySQL.

- Configured database connections.
- Implemented SQL operations.
- Loaded transformed records.
- Validated the resulting database records.

## ETL Architecture

```text
        CSV Files / Source Database
                    |
                    v
             Talend Open Studio
                    |
                    v
             Data Extraction
                    |
                    v
           Data Transformation
               (tMap)
                    |
                    v
              Data Loading
                    |
                    v
             MySQL Database
                    |
                    v
          Business Intelligence
               (Power BI)
```

## Project Structure

```text
talend-etl-data-integration/
|
|-- jobs/
|   |-- TP3_ex1/
|   |-- TP3_ex2/
|
|-- datasets/
|   |-- products.csv
|   |-- customers.csv
|   |-- sales.csv
|
|-- sql/
|   |-- create_tables.sql
|   |-- queries.sql
|
|-- screenshots/
|   |-- talend-workflow.png
|   |-- tmap-transformation.png
|   |-- mysql-results.png
|
|-- docs/
|   |-- etl-architecture.png
|
|-- README.md
|-- .gitignore
|-- LICENSE
```

## Project Results

- Successfully implemented ETL workflows.
- Applied conditional data transformations.
- Integrated multiple datasets using tMap.
- Automated data loading into MySQL.
- Verified data integration results.

## Screenshots

### Talend ETL Workflow

![Talend Workflow](screenshots/talend-workflow.png)

### Data Transformation Using tMap

![tMap Transformation](screenshots/tmap-transformation.png)

### MySQL Database Results

![MySQL Results](screenshots/mysql-results.png)

## Future Improvements

- Implement data quality checks.
- Add automated error handling.
- Introduce ETL pipeline monitoring.
- Develop Power BI dashboards.
- Improve pipeline performance.

## Author

**Ons Elfekih**

Business Intelligence Engineering Student

GitHub: [OnsElfekih](https://github.com/OnsElfekih)
