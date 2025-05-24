🏢 Adventure Works Data Engineering Project with Azure Data Platform
This project demonstrates a complete data engineering pipeline using the Adventure Works dataset. It involves ingestion, transformation, storage, and reporting using Azure Data Factory (ADF), Azure Data Lake Storage Gen2 (ADLS), Azure Databricks, Azure Synapse Analytics, and Power BI. The solution is built on a Medallion Architecture to ensure scalability, security, and efficient data processing.

📁 Project Architecture
Medallion Architecture Layers:
Bronze Layer: Raw data ingested from REST API into ADLS via ADF.

Silver Layer: Cleaned and transformed data stored in structured formats.

Gold Layer: Aggregated and curated data ready for business intelligence.

⚙️ Tech Stack
Azure Data Factory (ADF): Orchestrates and automates REST API data ingestion workflows using dynamic parameters.

Azure Data Lake Storage Gen2 (ADLS): Stores raw, cleaned, and curated datasets across Bronze, Silver, and Gold containers.

Azure Databricks: Performs transformations on raw data using PySpark and writes results back in optimized Delta format.

Azure Synapse Analytics: Consumes transformed data and creates external tables/views for fast query performance.

Power BI: Builds real-time, interactive dashboards for analytics and business reporting.

Service Principal Authentication: Secures access between ADF, Databricks, and ADLS.

🔄 Data Flow
Data Source:
Adventure Works data is dynamically fetched via REST API using ADF pipelines.

Bronze Layer (ADF):
ADF dynamically pulls raw data through REST API calls.

A ForEach loop iterates through datasets, loads them into Bronze container in ADLS using Copy Activity.

Silver Layer (Azure Databricks):
Databricks reads raw data from Bronze layer.

Performs cleaning, joins, filtering, partitioning, and reshaping using PySpark.

Writes transformed data to Silver container in Delta format.

Gold Layer (Databricks + Synapse):
Refined business logic applied in Databricks for aggregations and KPIs.

Final datasets written in Gold container and made queryable via Synapse external tables and views.

Reporting (Power BI):
Power BI connects to Synapse external tables for live dashboarding.

Enables real-time insights on Adventure Works sales, customers, products, and orders.

🧱 Components
Azure Data Factory
Pipelines with dynamic REST API calls

ForEach loops + Copy Activity

Parameterized Linked Services, Datasets

Monitoring, alerts, and scheduled triggers

Azure Data Lake Storage Gen2
Containers for: bronze/, silver/, gold/

Stores all raw, intermediate, and refined data

Azure Databricks
Notebooks for:

Data reading and writing to/from ADLS

Data transformations using PySpark

Writing in Delta format

Azure Synapse Analytics
External tables/views over Delta format files

SQL-based reporting queries

Power BI
Connected to Synapse for data visualization

Real-time reporting on business metrics

