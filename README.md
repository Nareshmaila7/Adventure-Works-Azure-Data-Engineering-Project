# 🏢 Adventure Works Data Engineering with Azure Data Platform

This project is designed to ingest, transform, and analyze Adventure Works data using Azure Data Factory (ADF), Azure Data Lake Storage (ADLS), Azure Databricks, Azure Synapse Analytics, and Power BI. The pipeline follows a Medallion Architecture (Bronze, Silver, Gold) to ensure data quality, reliability, and effective reporting.

---

## 📁 Project Architecture

![Project Architecture]https://github.com/Nareshmaila7/Adventure-Works-Azure-Data-Engineering-Project/blob/e033110758e127e93de21afff355b3eb68710e11/Project%20Architecture.png

**Medallion Architecture Layers:**

- **Bronze Layer:** Raw data ingested via REST API using ADF, dynamically parameterized to fetch Adventure Works data.
- **Silver Layer:** Cleaned and transformed data using Azure Databricks and stored in a curated Silver container.
- **Gold Layer:** Final processed data published to Azure Synapse and exported for reporting and analysis in Power BI.

---

## ⚙️ Tech Stack

- **Azure Data Factory (ADF):** For REST API-based ingestion and orchestration workflows.
- **Azure Data Lake Storage Gen2 (ADLS):** For Bronze, Silver, and Gold layer storage.
- **Azure Databricks:** For scalable data transformation using PySpark and Delta Lake.
- **Azure Synapse Analytics:** For external table creation and data modeling on curated data.
- **Power BI:** For dashboarding and business insights visualization.
- **Service Principal Authentication:** For secure access between ADF, ADLS, and Databricks.

---

## 🔄 Data Flow

1. **Data Ingestion (ADF + REST API)**  
   - REST API endpoint dynamically parameterized.
   - ADF pipelines fetch and land data into the **Bronze** container in ADLS.

2. **Bronze to Silver (Databricks)**  
   - Raw data from Bronze is read in Azure Databricks.
   - Data transformations applied using PySpark (filtering, aggregation, joins, etc.).
   - Transformed data stored in the **Silver** layer of ADLS.

3. **Silver to Gold (Databricks → Synapse)**  
   - Silver data further refined and loaded into **Azure Synapse Analytics**.
   - Views and external Delta tables created for reporting.
   - Data also written to the **Gold** container in ADLS.

4. **Reporting (Power BI)**  
   - Power BI connects to Synapse tables and Gold layer Delta files.
   - Interactive dashboards created for analytics and decision-making.

---

## 🧱 Components

### Azure Data Factory (ADF)
- Pipelines calling REST API with dynamic parameters.
- Copy activities to ingest data into ADLS.
- Linked services and datasets configured for secure API and storage access.

### Azure Data Lake Storage (ADLS)
- Containers: `bronze/`, `silver/`, `gold/` implementing Medallion architecture.
- Serves as the central data lake for raw and processed data.

### Azure Databricks
- Notebooks developed for:
  - Reading data from Bronze.
  - Performing filtering, joins, aggregations, and complex transformations.
  - Writing output to Silver and Gold containers in Delta format.

### Azure Synapse Analytics
- Created external Delta tables and views on Silver data.
- Used for enterprise-scale querying and BI connectivity.

### Power BI
- Connected to Synapse and Gold Delta files.
- Designed dashboards and reports for data insights.

---

## 📌 Summary

This project showcases an end-to-end data engineering solution on Azure with modular architecture. It automates ingestion, enables scalable transformation with PySpark, supports enterprise reporting, and aligns with real-world cloud data lake best practices.
