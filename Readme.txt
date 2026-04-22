Assignement API Data Ingestion & Analytics

Overview
This project implements an end-to-end data pipeline to ingest, transform, and analyze FHIR API healthcare data using Spark and Delta Lake.

Architecture
Raw → Bronze → Silver → Gold (Medallion Architecture)

Data Sources
FHIR API:
- Patient
- Encounter
- Observation
- Condition

 Features
- Incremental ingestion using `_lastUpdated`
- Pagination handling
- Nested JSON parsing
- Metadata tracking (extraction_timestamp, source)
- SCD Type 2 implementation for Patient
- Delta Lake storage and merge operations

 Pipeline Flow
Patient → Encounter → Observation → Condition

 Layers

 Raw Layer
Stores API responses as JSON (as-is)

 Bronze Layer
Parsed and structured Delta tables with metadata

Silver Layer
Cleaned and deduplicated data

 Gold Layer
Analytics-ready tables with aggregations and SCD implementation

Visualization
Gold layer connected to Power BI for reporting:
- Patient demographics
- Encounter status
- Observation trends
- Condition distribution

Tools Used
- Azure Databricks
- PySpark
- Delta Lake
- Power BI