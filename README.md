# AWS End-to-End Data Engineering Project

An end-to-end AWS Data Engineering project that demonstrates how raw support log and ticket data is ingested, transformed, stored in a data warehouse, and visualized through interactive Power BI dashboards.

## Tech Stack

- Amazon S3
- AWS Lambda (Python)
- AWS Glue (Visual ETL & PySpark)
- Amazon Athena
- Amazon Redshift
- Power BI
- Python
- SQL

---

## Project Architecture
                         PIPELINE 1 - SUPPORT LOGS

Log Files (.txt)
      │
      ▼
 Amazon S3 (Raw)
      │
      ▼
AWS Lambda (Python ETL)
- Data Cleaning
- Data Validation
- Convert to Parquet
      │
      ▼
Amazon S3 (Processed - Parquet)
      ├──────────────────────────►
      │
      ▼
 Amazon Athena (Ad Hoc Analysis)
      │
      ▼
 Amazon RedShift (Data WArehouse)


──────────────────────────────────────────────────────────────────────────────


                        PIPELINE 2 - SUPPORT TICKETS

Ticket Files
      │
      ▼
 Amazon S3 (Raw)
      │
      ▼
AWS Glue Visual ETL
- Data Cleaning
- Data Transformation
- Convert to Parquet
      │
      ▼
Amazon S3 (Processed - Parquet)
      │
      ▼
 Amazon Redshift(Data Warehouse)


──────────────────────────────────────────────────────────────────────────────


                  DATA WAREHOUSE

Amazon Redshift
   ├── support_logs
   └── support_tickets


──────────────────────────────────────────────────────────────────────────────

---

## Project Workflow

### Pipeline 1 – Support Logs

- Upload raw log files to Amazon S3.
- S3 triggers an AWS Lambda function.
- Python ETL script cleans and validates data.
- Data is converted to Parquet format.
- Processed files are stored back in Amazon S3.
- Athena is used for ad hoc SQL analysis.
- Data is loaded into Amazon Redshift.

### Pipeline 2 – Support Tickets

- Upload ticket files to Amazon S3.
- AWS Glue Visual ETL performs data transformation.
- Data is converted to Parquet format.
- Processed files are stored in Amazon S3.
- Data is loaded into Amazon Redshift.
- Power BI is used for dashboard creation.
- The Glue Visual ETL job was later converted into a PySpark script for automation.

---


---

## Key Features

- Automated data ingestion using AWS Lambda.
- ETL using Python and AWS Glue.
- Conversion of raw text files into Parquet format.
- Data lake architecture using Amazon S3.
- Ad hoc analytics using Amazon Athena.
- Data warehouse implementation with Amazon Redshift.
- Interactive Power BI dashboards.
- Glue Visual ETL converted into reusable PySpark code.

---

## Sample SQL Operations

- CREATE TABLE
- COPY Commands
- Data Validation Queries
- Aggregation Queries
- Analytical Queries

---


## Author

**Vijay N**

**Skills:** AWS • Python • SQL • Power BI • Amazon Redshift • AWS Glue • Amazon Athena • Amazon S3
                         
                         
                         
