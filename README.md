# Netflix-Azure-Data-Engineering-Project
This project demonstrates an end-to-end Azure-based data engineering pipeline for ingesting, processing, transforming, and serving Netflix shows metadata. We leverage public CSV datasets from Kaggle, store raw data in GitHub and Azure Data Lake Storage (ADLS), orchestrate pipelines with Azure Data Factory, process data in Databricks using Autoloader and Delta Lake, and deliver insights via Delta Live Tables to Power BI and Azure Synapse.

# Architecture Overview
<img width="790" alt="image" src="https://github.com/user-attachments/assets/ba391cb2-4aa4-4fec-a8ea-d8a7187fc59a" />

1. Ingestion: Raw CSVs from GitHub and ADLS Raw container ingested via ADF & Databricks Autoloader.

2. Processing: Bronze ➔ Silver via PySpark notebooks for cleansing, normalization, and validation.

3. Serving: Silver ➔ Gold using Delta Live Tables for distilled, aggregated tables.

4. Consumption: Gold layer tables accessible for reporting & analytics in Power BI and Azure Synapse.

## Data Sources
<link> https://public.tableau.com/app/learn/sample-data </link>
<br>
https://www.kaggle.com/datasets/shivamb/netflix-shows

## Azure Resources & Tools

1. Azure Data Factory: Pipeline orchestration, scheduling, and monitoring

2. Azure Data Lake Storage Gen2: Raw, bronze, silver, gold containers

3. Azure Databricks:

4. Autoloader: Incremental ingestion from ADLS

5. PySpark Notebooks: Data cleansing & transformation

6. Delta Lake: ACID transactional storage for bronze/silver/gold

7. Delta Live Tables: Declarative pipeline for transforming and serving data

8. Power BI: Data visualization via Partner Connect

9. Azure Synapse Analytics: Data warehouse for advanced analytics

10. CI/CD: Azure DevOps / GitHub Actions for deployment of ADF pipelines & Databricks notebooks

## Pipeline Workflow

### 1. Raw Ingestion (Bronze)

Azure Data Factory pulls CSVs from GitHub every night.

Databricks Autoloader ingests new files from ADLS raw container into Bronze parquet/Delta tables.

Bronze Tables contain raw, schema-on-read data, partitioned by ingestion date.

### 2. Cleansing & Transformation (Silver)

PySpark Notebooks perform:

Schema enforcement & type casting

Null handling & deduplication

Lookup enrichment (e.g., mapping country codes)

Silver Tables store cleaned, conformed data ready for analytics.

### 3. Aggregation & Serving (Gold)

Delta Live Tables define transformations:

Aggregate metrics (e.g., shows per category, director counts)

Time-series snapshots

Star-schema conformed fact & dimension tables

Gold Tables are optimized for query performance and reporting.

## Delta Live Tables & Serving

**Pipeline Definition:** Python-based DLT pipelines stored in dlt/.

**Quality Checks:** Declarative assertions on data freshness, completeness.

**Outputs:** Gold Delta tables available in Databricks and registered in Unity Catalog.

## Deployment & CI/CD

**Git Integration:** All code (pipelines, notebooks, DLT definitions) in GitHub.

**Azure DevOps Pipelines / GitHub Actions:**

  1. Validate ARM templates & notebooks

  2. Deploy ADF pipelines, Databricks workspace artifacts, and DLT pipelines

  3. Automated testing of notebook jobs

## Monitoring & Data Quality

1. Azure Data Factory monitoring for pipeline runs & alerts

2. Databricks job dashboards & cluster logs

3. Delta Live Tables built‑in data quality policies & metrics

4. Azure Monitor for logging and alerting on failures or SLA breaches

















