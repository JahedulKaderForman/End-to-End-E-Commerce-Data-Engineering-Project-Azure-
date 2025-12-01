# 📦 End-to-End E-Commerce Data Engineering Project (Azure)
This project showcases my end-to-end cloud data engineering work using the Azure ecosystem. I built a complete data pipeline that simulates how an e-commerce business processes customer, product, and sales data to generate meaningful insights. The solution follows the  **Medallion Architecture (Bronze → Silver → Gold) ** and uses  **Azure Data Factory, Azure Databricks, Azure Synapse Serverless SQL, and Power BI ** to create a production-style analytics platform.

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

<img width="1116" height="542" alt="architecture_e_com" src="https://github.com/user-attachments/assets/5b7949b4-6c8a-488e-8265-8944153503c5" />



### Architecture Flow

<img width="931" height="367" alt="image" src="https://github.com/user-attachments/assets/bd279c7b-e0e1-468e-99df-fc507bc4f24b" />



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


<img width="1476" height="727" alt="data_lake_1" src="https://github.com/user-attachments/assets/5cb077a8-9853-4aef-b59a-ae5affbef2ee" />





---

# 🧠 Data Modeling

<img width="1006" height="725" alt="data_modeling" src="https://github.com/user-attachments/assets/7dcc59a3-c253-474e-9ef4-83477c592b94" />


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

<img width="1455" height="635" alt="adf" src="https://github.com/user-attachments/assets/b0ceaccf-4db4-4646-97d5-76714568de22" />



### 🔹 Silver Layer  
Cleaned + standardized:
- Fixed data types  
- Removed duplicates  
- Derived fields

<img width="1802" height="783" alt="databricks_2" src="https://github.com/user-attachments/assets/84ee2981-ebc3-4075-a713-df1318ca0a61" />


### 🔹 Gold Layer  
Business-ready:
- Dimensional tables (customer, product, date)
- Fact table (order-level sales metrics)
- Loaded to Synapse for reporting

<img width="1790" height="762" alt="databricks_3" src="https://github.com/user-attachments/assets/90e06cb1-2aa6-4914-8dbc-dc91affeca81" />

<img width="1547" height="863" alt="syanpse_3" src="https://github.com/user-attachments/assets/26a5c835-c0bf-4ffa-b7d9-c67bfd48f667" />



Transformations performed using **PySpark notebooks in Azure Databricks**.

---

# 📈 Power BI Dashboard

<img width="1262" height="710" alt="report" src="https://github.com/user-attachments/assets/d908ad7c-d0a4-40a1-ba9b-44fe3646dbd8" />


Dashboard includes:
- Total revenue  
- Monthly sales trend  
- Sales by category  
- Top-selling products  
- Orders by country  
- Customer insights  

---

# 📁 Project Structure



