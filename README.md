🏭 Adventure Works Data Engineering Project with Azure Data Platform
This project ingests, transforms, and analyzes Adventure Works enterprise data using Azure Data Factory (ADF), Azure Data Lake Storage Gen2 (ADLS), Azure Databricks, Azure Synapse Analytics, and Power BI. It implements a Medallion Architecture (Bronze, Silver, Gold) for scalable, reliable, and maintainable data processing.

📁 Project Architecture:

![Project Architecture]https://github.com/Nareshmaila7/Adventure-Works-Azure-Data-Engineering-Project/blob/060875cbfea115d2d6d8ad0e5613db85dd38947c/Project%20Architecture.png

Medallion Architecture Layers:
Bronze Layer: Raw data ingested dynamically from the Adventure Works REST API endpoint into ADLS Gen2.

Silver Layer: Cleaned, transformed data using Azure Databricks and PySpark for refined analytics.

Gold Layer: Curated and modeled data stored in ADLS and Azure Synapse Analytics, optimized for reporting and BI.


⚙️ Tech Stack:
Azure Data Factory (ADF): Orchestrates data ingestion and pipeline automation.

Azure Data Lake Storage Gen2 (ADLS): Stores raw and processed datasets across Medallion layers.

Azure Databricks: Executes scalable data transformations with PySpark, applying business logic and optimizations.

Azure Synapse Analytics: Hosts external tables and views for SQL-based analytics and fast querying.

Power BI: Provides interactive dashboards and real-time reporting connected to Synapse.

Service Principal Authentication: Securely manages access between ADF, Databricks, and ADLS.


🔄 Data Flow:
Data Source
Adventure Works data pulled dynamically through REST API calls with parameterized pipelines in Azure Data Factory.

Bronze Layer (ADF)
ADF pipelines ingest raw data into the Bronze container in ADLS Gen2, maintaining immutable raw data.

Silver Layer (Databricks)
Databricks reads raw data from Bronze.

Performs cleaning, filtering, joins, repartitioning, and other transformations.

Writes cleaned data to the Silver container in ADLS.

Gold Layer (Synapse + ADLS)
Further aggregation and modeling done in Azure Synapse Analytics.

External tables and views created on Silver data for optimized SQL querying.

Curated data saved in Gold container on ADLS.

Reporting (Power BI)
Power BI connects to Synapse to build dynamic dashboards and business reports for insights.


🧱 Components:
Azure Data Factory: Parameterized pipelines with REST API integration, monitoring, triggers, and alerts.

ADLS Gen2: Organized storage in bronze/, silver/, and gold/ folders following Medallion Architecture.

Azure Databricks: PySpark notebooks for data transformation, optimization, and Delta Lake storage.

Azure Synapse Analytics: SQL scripts for modeling and external table creation.

Power BI: Interactive reports connected to Synapse SQL pools.


🎯 Key Achievements:
Built scalable, reusable data pipelines using Azure services.

Implemented Medallion Architecture for reliable data layering.

Enhanced performance with Spark tuning (broadcast joins, repartitioning).

Enabled real-time BI reporting with Power BI connected to Synapse.

Secured data access via service principal authentication across Azure resources.

