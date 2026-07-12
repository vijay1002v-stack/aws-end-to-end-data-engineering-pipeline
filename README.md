# aws-end-to-end-data-engineering-pipeline
Built an end-to-end AWS Data Engineering pipeline that ingests raw log files and MySQL ticket data, transforms the data using AWS Lambda and AWS Glue, stores optimized Parquet files in Amazon S3, loads curated data into Amazon Redshift, and visualizes business insights using Power BI.

## Project Architecture

```text
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
      ├──────────────────────────► Amazon Athena (Ad Hoc Analysis)
      │
      ▼
 Amazon Redshift
      │
      ▼
 Power BI Dashboard


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
 Amazon Redshift
      │
      ▼
 Power BI Dashboard


──────────────────────────────────────────────────────────────────────────────


                  DATA WAREHOUSE

Amazon Redshift
   ├── support_logs
   └── support_tickets


──────────────────────────────────────────────────────────────────────────────


Automation:
AWS Glue Visual ETL → Converted to PySpark Script for automated execution.
```
