# 🚖 NYC Taxi End-to-End Data Engineering Project  

An interactive **end-to-end data engineering pipeline** built on **Azure**, using the **NYC Taxi dataset** as a real-world case study. This project demonstrates how to design scalable pipelines, handle real-time ingestion, transform raw data into analytics-ready formats, and serve insights with modern cloud tools.  

---  

## ✨ Project Overview  

- **Data Source**: NYC Taxi public dataset (Parquet format + Lookup CSVs)  
- **Architecture**: Follows the **Medallion Architecture** (Bronze → Silver → Gold)  
- **Pipeline Type**: **Dynamic & Parameterized** pipelines using **Azure Data Factory (ADF)**  
- **Processing Engine**: **Databricks + PySpark** for transformations  
- **Storage**: **Azure Data Lake Storage Gen2 (ADLS)** with Delta Lake  
- **Serving Layer**: Data made available for **Power BI / analytics tools**  
- **Security**: Managed Identities + Role-based Access  

---  

## 🏗️ Architecture  

```mermaid
flowchart LR
    API[NYC Taxi API] --> ADF[Azure Data Factory: Dynamic Pipelines] --> Bronze[Bronze Layer (Raw Data)]
    Bronze -->|PySpark in Databricks| Silver[Silver Layer (Cleaned & Processed)]
    Silver -->|Delta Lake (ACID, Time Travel)| Gold[Gold Layer (Analytics-Ready)]
    Gold --> PowerBI[Power BI / Analytics Tools]
```  

- **Bronze Layer**: Raw parquet files fetched dynamically from APIs  
- **Silver Layer**: Cleaned, structured data with applied business rules  
- **Gold Layer**: Curated, optimized Delta tables for BI and ML use cases  

---  

## 🔑 Key Features  

- 📡 **Dynamic API Ingestion**: Automated monthly pulls (no manual uploads!)  
- 🔄 **Parameterized Pipelines**: Reusable ADF datasets, linked services, loops  
- 🗂️ **Delta Lake**: Versioning, time-travel, ACID transactions, schema evolution  
- ⚡ **PySpark Optimizations**: Partitioning, transformations, and data quality checks  
- 🔐 **Security Best Practices**: Managed identities for access control  
- 📊 **Analytics Ready**: Gold data directly consumed by Power BI dashboards  

---  

## 🛠️ Tech Stack  

- **Cloud**: Azure (Data Factory, Databricks, ADLS Gen2)  
- **Processing**: PySpark, Delta Lake  
- **Storage Format**: Parquet + Delta  
- **Visualization**: Power BI  
- **Version Control & CI/CD**: GitHub + Git  

---  

## 🚀 Workflow  

1. **Ingestion**  
   - ADF dynamically calls NYC Taxi APIs  
   - Monthly data pulled into **Bronze Layer** (Parquet format)  

2. **Processing**  
   - Databricks (PySpark) cleans & transforms  
   - Writes results into **Silver Layer**  

3. **Enrichment**  
   - Lookup data (Taxi Zones) joined at Silver stage  
   - Schema evolution + partitioning applied  

4. **Curated Gold Data**  
   - Delta tables with **time travel & ACID guarantees**  
   - Ready for **reporting, ML, and analytics**  

5. **Consumption**  
   - Power BI connects directly to Gold layer  
   - Interactive dashboards for insights  

---  

## 📂 Project Structure  

```
NYC-Taxi-DataEngineering-Project/
│── data/                # Sample lookup CSVs  
│── notebooks/           # PySpark transformation notebooks  
│── pipelines/           # ADF JSON pipeline definitions  
│── docs/                # Architecture diagrams & notes  
│── README.md            # Project documentation  
```  

---  

## 📈 Outcomes  

- ✅ Automated ingestion from APIs (no manual effort)  
- ✅ Optimized transformations using PySpark & Databricks  
- ✅ Reliable storage with Delta Lake (ACID, time travel, schema evolution)  
- ✅ Analytics-ready data served directly to Power BI  

---  

## 🎯 Why This Project Matters  

This project is a **complete data engineering pipeline** that reflects **real-world practices** used in the industry. It covers:  
- Data ingestion at scale  
- Transformation using Spark-based frameworks  
- Data governance with Delta Lake  
- BI-ready serving layer for analytics  

It’s not just a demo — it’s an **end-to-end implementation** showing how raw data turns into business-ready insights.  

---  

## 📌 Next Steps  

- Add real-time streaming ingestion with **Azure Event Hubs**  
- Extend governance with **Unity Catalog**  
- Deploy CI/CD pipelines for production readiness  

---  

## 🧑‍💻 Author  

**Tushar Kaushik**  
🎓 MS in Applied Data Science — University of Southern California (USC)  
🔗 [LinkedIn](https://www.linkedin.com/in/tushar-kaushik-493a8115a/) | 📧 kaushiktk015@gmail.com  

---  
