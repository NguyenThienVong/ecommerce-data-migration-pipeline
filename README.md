# Preface

This project is a beginner-friendly Data Engineering project focused on migrating e-commerce data from SQL Server to PostgreSQL.

The project simulates a real-world data migration and ETL workflow. The source database contains more than 1 million records, including several intentional data quality issues.

The main goal is to practice the fundamentals of Data Engineering:

- SQL
- Python
- Pandas
- ETL
- Data Cleaning
- Data Quality
- Batch Processing
- PostgreSQL
- Data Validation

# Tools & Technologies
- SQL Server — Source database
- Python — ETL and data processing
- Pandas — Data transformation and cleaning
- pyodbc — SQL Server connection
- psycopg2 — PostgreSQL connection
- Jupyter Notebook — Exploration and testing
- PostgreSQL — Target database
- Git & GitHub — Version control

# Project Workflow

## High-level

The migration process follows these main steps:

1 Generate and prepare source data in SQL Server
2 Explore and audit the source data
3 Extract data from SQL Server
4 Clean and transform the data using Python/Pandas
5 Load the transformed data into PostgreSQL
6 Validate the migrated data
7 Generate a simple validation report

## Low-level

1. Setup Environment

- Create a Python virtual environment
- Install required Python libraries
- Create a .env file
- Store database connection information in environment variables
- Test connections to SQL Server and PostgreSQL

2. Prepare Source Data
- Generate sample e-commerce data
- Create the following tables:
Categories
Suppliers
Customers
Products
- Insert approximately 1 million+ records into SQL Server
- Include some intentional data quality issues for ETL practice

3. Audit Source Data

Before migration:

- Check the number of rows in each table
- Check column names and data types
- Check NULL values
- Check duplicate records
- Check invalid values
- Check invalid email formats
- Check negative prices or stock quantities
- Check invalid foreign key relationships

4. Extract Data

For each table:

- Connect to SQL Server using pyodbc
- Read the data using SQL queries
- Load the data into Pandas DataFrames
- Process large tables in batches when necessary

5. Transform Data

Clean and standardize the data using Python/Pandas:

- Convert column names to lowercase
- Handle NULL values
- Remove or fix invalid records
- Validate email formats
- Fix invalid dates
- Handle negative prices
- Handle negative stock quantities
- Check invalid foreign keys
- Convert data types to appropriate PostgreSQL types

6. Load Data

- Connect to PostgreSQL using psycopg2
- Create the target tables
- Load transformed data into PostgreSQL
- Use batch inserts for large datasets
- Commit the data after successful loading

7. Validate Migration

After loading:

- Compare row counts between SQL Server and PostgreSQL
- Check that important columns were migrated correctly
- Check NULL values
- Check data types
- Check primary key uniqueness
- Check foreign key relationships
- Check sample records between source and target

8. Generate Validation Report

Create a simple report containing:

- Source row count
- Target row count
- Number of migrated records
- Number of rejected/cleaned records
- Data quality issues found
- Validation results
- Migration status
- Final Data Flow

SQL Server

↓

Extract

↓

Python / Pandas

↓

Transform & Data Cleaning

↓

Validate

↓

PostgreSQL

↓

Post-Migration Validation

↓

Validation Report