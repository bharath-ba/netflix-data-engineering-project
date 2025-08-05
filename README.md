# netflix-data-engineering-project

This project demonstrates a complete **Data Engineering Pipeline** using Azure’s data services. The solution processes, transforms, and delivers data for **Business Intelligence (BI)** reporting using:

- **Azure Data Factory**
- **Azure Databricks**
- **Azure Synapse Analytics**
- **Power BI**

📊 **Data Source**: [AdventureWorks Dataset](https://github.com/) (fetched via HTTP from GitHub)

---

## 📌 Architecture Overview

```text
GitHub (Raw Data) 
   ↓ (HTTP API)
Azure Data Factory (ADF)
   ↓
Azure Data Lake Storage (Bronze → Silver → Gold)
   ↓
Azure Databricks (Transformation)
   ↓
Azure Synapse Analytics (Warehousing & SQL)
   ↓
Power BI (Reporting & Dashboards)
```

---

## ⚙️ Step 1: Setting Up the Azure Environment

Provisioned the following Azure services:

- 🔄 **Azure Data Factory** – Orchestration & automation
- 🪣 **Azure Storage Account** – Data lake with `bronze`, `silver`, `gold` containers
- 🔧 **Azure Databricks** – Data transformation & processing
- 🏛 **Azure Synapse Analytics** – Serverless SQL for warehousing
- 📊 **Power BI** – Data visualization and reporting

✅ All services were connected with proper **IAM roles** to ensure secure and seamless data movement.

---

## 🚀 Step 2: Ingesting Data Using Azure Data Factory

- **HTTP Connector**: ADF fetches raw data directly from GitHub.
- **Dynamic Parameters**: Pipeline supports parameterization for flexible data sources.
- **Sink**: Raw data is stored in the **bronze layer** of Azure Storage.

📁 **Output**: `.csv` or `.json` files stored in `bronze/`

---

## 🔄 Step 3: Data Transformation with Azure Databricks

**Databricks Process**:
- 🔥 Cluster setup for efficient processing
- 📂 Connected to Azure Storage for reading `bronze` data

**Transformations**:
- Normalized inconsistent date formats
- Removed nulls, invalid, and incomplete rows
- Aggregated & joined data for analysis-readiness

📁 **Output**: Cleaned data saved in `silver/` as **Parquet** format

---

## 📊 Step 4: Warehousing with Azure Synapse Analytics

- Connected to **Silver** container in Azure Data Lake
- Utilized **Serverless SQL Pools** to query directly from Parquet files
- Created:
  - External Tables
  - Views
  - SQL Database and Schema for BI tools

📁 **Output**: Curated `gold` dataset ready for reporting

---

## 📈 Step 5: BI Dashboarding with Power BI

- Connected Power BI to Azure Synapse
- Built dashboards to visualize key KPIs:
  - Sales performance
  - Product categories
  - Customer geography
  - Year-over-year comparisons

📊 **Goal**: Deliver meaningful insights to business stakeholders

---

## ✅ Key Takeaways

| Benefit        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| 🚀 Automation  | Seamless, no-code orchestration via ADF                                      |
| ☁️ Scalability | Azure services handle enterprise-scale workloads                             |
| 📦 Efficiency  | Parquet format + serverless querying = fast, low-cost analytics              |
| 📊 Insightful  | Power BI integration enables interactive and real-time decision making       |

---

## 🙌 Acknowledgments

Inspired by the brilliant work of **Ansh Lamba**.  
Check out his [GitHub](https://github.com/) and [YouTube Channel](https://www.youtube.com/) for in-depth tutorials and walkthroughs.

---

## 📎 Useful Links

- 🔗 [Azure Data Factory](https://learn.microsoft.com/en-us/azure/data-factory/)
- 🔗 [Azure Databricks](https://learn.microsoft.com/en-us/azure/databricks/)
- 🔗 [Azure Synapse Analytics](https://learn.microsoft.com/en-us/azure/synapse-analytics/)
- 🔗 [Power BI](https://powerbi.microsoft.com/)

---

## 📂 Project Structure

```bash
azure-e2e-pipeline/
├── adf-pipeline/
│   └── pipeline.json
├── databricks-notebooks/
│   └── transform_data.ipynb
├── synapse-sql/
│   └── external_tables.sql
├── powerbi/
│   └── dashboard.pbix
├── README.md
```

---

## ✉️ Contact

Have questions or want to collaborate?

- 📧 your.email@example.com
- 🔗 [LinkedIn](https://linkedin.com/in/your-profile)

---