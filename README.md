# Assignment-on-Azure-Data-Analytics-Smartgear-Sales
End-to-End Azure Data Engineering project using Data Factory, Databricks, and Synapse — automated ETL, transformation, and analytics for SmartGear sales data.

## Project Overview
The **SmartGear Azure Data Engineering Project** demonstrates how to design and implement a **complete cloud-based data pipeline** using **Microsoft Azure**.  
The goal is to automate the ingestion, transformation, and analysis of SmartGear’s sales data, enabling scalable, efficient, and real-time insights for business decision-making.

This project integrates multiple Azure services:
- **Azure Data Factory** for data movement and orchestration  
- **Azure Databricks** for transformation and aggregation using Apache Spark  
- **Azure Synapse Analytics** for ad-hoc querying  
- **Azure Data Lake Gen2** for storage across Raw, Landing, and Curated zones  

## Objectives
1. Ingest sales data into a centralized Azure Data Lake.  
2. Automate ETL processes with Azure Data Factory.  
3. Transform and aggregate data using Azure Databricks notebooks.  
4. Query curated data using Synapse serverless SQL.  
5. Deliver a seamless, repeatable data workflow ready for enterprise scaling.


## Tasks Summary

| Task | Description | Deliverable |
|------|--------------|-------------|
| **A** | Azure setup — Resource Group & Storage Account creation | `stsaketsharmasmartgear` with `raw`, `landing`, `curated` containers |
| **B** | Databricks ETL – Aggregate total quantity by region | `taskB_smartgear.ipynb`, output: `region_qty.parquet` |
| **C** | Synapse – Query top 5 rows of curated parquet file | `taskC.png` |
| **D** | Data Factory – Pipeline automating Raw → Landing | `taskD.json` |
| **E** | Reflection Memo – Lessons Learned | `reflection.md` |


## Tools & Technologies

| Category | Service | Purpose |
|-----------|----------|----------|
| Storage | Azure Data Lake Gen2 | Store raw, landing, and curated data |
| Orchestration | Azure Data Factory | Automate and schedule ETL pipelines |
| Transformation | Azure Databricks | Clean and aggregate data using Spark |
| Analytics | Azure Synapse Analytics | Ad-hoc SQL queries over parquet |
| Visualization | Power BI | Region-wise sales insights |
| Development | Python, PySpark, SQL | Data processing & analysis |


## Data Flow Summary

1. **Raw Zone:**  
   Upload the source file `smartgear_sales.csv` into `raw/`.

2. **Landing Zone (via ADF):**  
   Azure Data Factory pipeline copies data from `raw` → `landing`.

3. **Curated Zone (via Databricks):**  
   Databricks notebook cleans, filters, and aggregates sales data, saving the output parquet file `region_qty.parquet` in `curated/`.

4. **Analytics (via Synapse):**  
   Synapse serverless SQL queries the curated parquet file to generate insights.


## Key Learnings

- **Biggest Surprise:**  
  How tightly integrated Azure services are — once linked properly, storage, compute, and analytics flow seamlessly.

- **Challenge Faced:**  
  Subscription and region restrictions when provisioning Synapse and Databricks resources.  
  Fixed by switching regions and re-registering resource providers.

- **Data Factory vs. Databricks:**  
  - Use **ADF** for *data movement, orchestration, and automation*.  
  - Use **Databricks** for *data transformation, analysis, and machine learning*.



