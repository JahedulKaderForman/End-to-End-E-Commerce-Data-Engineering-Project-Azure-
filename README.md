# 📦 End-to-End E-Commerce Data Engineering Project (Azure)

This project demonstrates a **production-style cloud data engineering pipeline** built on Azure.  
It simulates how an e-commerce company processes product, customer, and sales data to build a modern analytics platform.

The solution follows a **medallion architecture (Bronze → Silver → Gold)** and uses **Azure Data Factory, Azure Databricks, Azure Synapse, and Power BI**.

---

## 📘 Table of Contents

1. [Project Overview](#project-overview)  
2. [Architecture](#architecture)  
3. [Tech Stack](#tech-stack)  
4. [Dataset](#dataset)  
5. [Data Lake Structure](#data-lake-structure)  
6. [Data Modeling](#data-modeling)  
7. [Transformation Pipeline](#transformation-pipeline)  
8. [Power BI Dashboard](#power-bi-dashboard)
   
---

# 🧩 Project Overview

The goal of this project is to build a **fully functional analytics ecosystem** for an e-commerce platform, covering:

- Data ingestion  
- Cloud storage (Data Lake)  
- Transformation using Apache Spark  
- Dimensional modeling (Star Schema)  
- Data warehousing in Synapse  
- Visualization using Power BI  

This project is designed to showcase **real-world data engineering skills** used in modern enterprises.

---

# 🏗️ Architecture

Below is the high-level architecture of the solution:

📌 **Replace with your diagram later:**  
`![Architecture Diagram](images/architecture.png)`

### Architecture Flow




---

# 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Ingestion | Azure Data Factory |
| Storage | Azure Data Lake Gen2 |
| Processing | Azure Databricks (PySpark) |
| Warehouse | Azure Synapse Analytics |
| Visualization | Power BI |
| Version Control | GitHub |

---

# 📊 Dataset

The project uses a small simulated e-commerce dataset with:

- **customers.csv**  
- **products.csv**  
- **orders.csv**  
- **order_items.csv**

This data includes customer info, product catalog, order headers, and order items.

---

# 📂 Data Lake Structure (Medallion Architecture)







---

# 🧠 Data Modeling

📌 **Replace with your diagram:**  
`![Data Model](images/data_model.png)`

The project uses a **Star Schema**:

### ⭐ Dimensions
- `dim_customer`
- `dim_product`
- `dim_date`

### ⭐ Fact Table
- `fact_order` (one row per order item)

---

# ⚙️ Transformation Pipeline

### 🔹 Bronze Layer  
Raw CSV files ingested from ADF.

### 🔹 Silver Layer  
Cleaned + standardized:
- Fixed data types  
- Removed duplicates  
- Derived fields  

### 🔹 Gold Layer  
Business-ready:
- Dimensional tables (customer, product, date)
- Fact table (order-level sales metrics)
- Loaded to Synapse for reporting  

Transformations performed using **PySpark notebooks in Azure Databricks**.

---

# 📈 Power BI Dashboard

📌 Placeholder for your screenshot:  
`![Power BI Dashboard](images/powerbi_dashboard.png)`

Dashboard includes:
- Total revenue  
- Monthly sales trend  
- Sales by category  
- Top-selling products  
- Orders by country  
- Customer insights  

---

# 📁 Project Structure



