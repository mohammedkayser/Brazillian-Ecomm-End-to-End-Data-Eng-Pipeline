# End-to-End Data Engineering Pipeline on Azure (Brazilian E-Commerce Dataset)

## 📌 Project Overview
This project demonstrates a complete **data engineering pipeline** built on **Microsoft Azure** using the [Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).  
The solution is designed with the **Medallion Architecture** (Bronze → Silver → Gold) to ensure scalable, reliable, and analytics-ready data processing.

---

## 🚀 Architecture Workflow

1. **Data Ingestion**  
   - Raw CSV files hosted on **GitHub** and a subset stored in a **SQL Database**.  
   - Used **Azure Data Factory (ADF)** pipelines to ingest data from:
     - GitHub (via HTTP connector).  
     - SQL Database (via JDBC connection).  
   - Landed all raw data into **Azure Data Lake Storage Gen2 (ADLS Gen2)** under the **Bronze layer**.

2. **Data Transformation & Enrichment**  
   - Leveraged **Azure Databricks (Spark)** for cleaning, joining, and transforming datasets.  
   - Added external enrichment data from **MongoDB**, ingested via Spark into **Bronze**.  
   - Produced structured and cleaned **Parquet files** stored in the **Silver layer**.

3. **Serving Layer**  
   - Used **Azure Synapse Analytics (Serverless SQL Pool)** to create external tables and final curated **views** from Silver data.  
   - Exposed business-ready datasets in the **Gold layer** for downstream analytics and visualization.

4. **Visualization / Consumption**  
   - The Gold layer datasets are ready for **BI dashboards** (Power BI, Tableau) or **Data Science workloads**.

---

## 🏗️ Azure Resources Used
- **Azure Data Factory (ADF)** → Data ingestion pipelines.  
- **Azure Data Lake Storage Gen2 (ADLS)** → Bronze, Silver, Gold layers.  
- **Azure Databricks** → Data transformation and enrichment.  
- **MongoDB (External)** → Enrichment dataset.  
- **Azure Synapse Analytics** → Serverless SQL pool for querying and serving.  

---

## 📂 Medallion Architecture

adls_gen2/
│── bronze/ → Raw ingested data (CSV, JSON, MongoDB extracts)
│── silver/ → Cleaned, transformed, joined data (Parquet)
│── gold/ → Curated data served via Synapse (Views / Tables)


---

## 🔄 Data Pipeline Flow

1. **Ingestion (ADF)**  
   - Pull raw CSV from GitHub.  
   - Load SQL DB tables.  
   - Store in **ADLS → Bronze**.  

2. **Transformation (Databricks)**  
   - Clean missing values, normalize columns.  
   - Join datasets (orders, payments, products, reviews, etc.).  
   - Enrich with MongoDB data.  
   - Store as **Parquet in Silver**.  

3. **Serving (Synapse)**  
   - Create external tables/views on Silver Parquet files.  
   - Expose as **Gold layer** for analytics.  

---

## 📸 Project Screenshots

1. **Azure Resources Overview**  
   *(_Insert screenshot of Azure portal homepage showing resources_)*  

2. **Medallion Architecture (Bronze, Silver, Gold Folders)**  
   *(_Insert screenshot of ADLS folder structure_)*  

3. **ADF Pipeline Workflow**  
   *(_Insert screenshot of ADF pipeline workflow_)*  

4. **Synapse Analytics Queries & Views**  
   *(_Insert screenshot of Synapse serving Gold layer_)*  

---

## 📊 Key Learnings
- Implemented the **Medallion Architecture** with Azure.  
- Built an **orchestrated ETL pipeline** using ADF + Databricks.  
- Designed a **scalable serving layer** with Synapse.  
- Practiced **cloud-native data engineering workflows** end-to-end.

---

## 🛠️ Tech Stack
- **Azure Data Factory**  
- **Azure Data Lake Storage Gen2**  
- **Azure Databricks (Apache Spark)**  
- **Azure Synapse Analytics**  
- **MongoDB (Enrichment Data)**  
- **Python, SQL**  

---

## 📌 Next Steps (Future Enhancements)
- Automate pipeline scheduling with **ADF triggers**.  
- Integrate **Power BI dashboards** directly with Gold layer.  
- Add **CI/CD deployment** for Databricks notebooks and ADF pipelines.  

---

## 📧 Contact
For questions or collaboration, feel free to connect!  


