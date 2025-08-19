# End-to-End Data Engineering Pipeline on Azure (Brazilian E-Commerce Dataset)

## 📌 Project Overview
This project demonstrates a complete **data engineering pipeline** built on **Microsoft Azure** using the [Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).  
The solution is designed with the **Medallion Architecture** (Bronze → Silver → Gold) to ensure scalable, reliable, and analytics-ready data processing.

---

<img width="1436" height="786" alt="Project_Architechure" src="https://github.com/user-attachments/assets/5abfadcf-0238-423d-ac89-c1776318c903" />

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

```bash
adls_gen2/
├── bronze/   # Raw ingested data (CSV, JSON, MongoDB extracts)
├── silver/   # Cleaned, transformed, joined data (Parquet)
└── gold/     # Curated data served via Synapse (Views / Tables)
```
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
   <img width="1272" height="415" alt="resources" src="https://github.com/user-attachments/assets/17f0eaea-d317-4ad8-a85a-93cf5119be9a" />

2. **Medallion Architecture (Bronze, Silver, Gold Folders)**  
   <img width="1126" height="543" alt="medillion" src="https://github.com/user-attachments/assets/a3092b95-2165-4d7b-8047-57c68d0e40bd" />

3. **ADF Pipeline Workflow**  
<img width="1761" height="655" alt="ADF" src="https://github.com/user-attachments/assets/9bf455c1-e0df-439e-9f25-68da1b33c90f" />

4. **Synapse Analytics Queries & Views**  
<img width="1529" height="869" alt="synapse" src="https://github.com/user-attachments/assets/1707c247-b48a-4d82-90ba-d0500eae0ebe" />
  
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

- 🌐 **Portfolio**: [mohamedkayser.com](https://mohamedkayser.com)  
- 💼 **LinkedIn**: [https://www.linkedin.com/in/mohammedkayser](https://www.linkedin.com/in/mohammedkayser)  
- 📩 **Email**: [mohammedkayser143@gmail.com](mailto:mohammedkayser143@gmail.com)  



