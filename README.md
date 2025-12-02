# 📦 End-to-End E-Commerce Data Engineering Project (Azure)
This project showcases my end-to-end cloud data engineering work using the Azure ecosystem. I built a complete data pipeline that simulates how an e-commerce business processes customer, product, and sales data to generate meaningful insights. The solution follows the **Medallion Architecture (Bronze → Silver → Gold)** and uses **Azure Data Factory**, **Azure Databricks**,**Azure Key Vault**, **Azure Synapse Serverless SQL**, and **Power BI** to create a production-style analytics platform.

🎥 **YouTube Walkthrough:** https://www.youtube.com/watch?v=nuK7y4Kc5tg

---

## 📘 Table of Contents

1. [Project Overview](#-project-overview)  
2. [Architecture](#%EF%B8%8F-architecture)  
3. [Tech Stack](#%EF%B8%8F-tech-stack)  
4. [Dataset](#-dataset)  
5. [Data Lake Structure](#-data-lake-structure-medallion-architecture)  
6. [Data Modeling](#-data-modeling)  
7. [Transformation Pipeline](#%EF%B8%8F-transformation-pipeline)  
8. [Power BI Dashboard](#-power-bi-dashboard)
   
---

# 🧩 Project Overview

I designed this project to demonstrate how raw operational data can be ingested, transformed, modeled, and visualized using modern cloud tools.  
The pipeline includes:

- Data ingestion  
- Cloud storage (Data Lake)  
- Transformation using Apache Spark  
- Dimensional modeling (Star Schema)  
- Data warehousing in Synapse  
- Visualization using Power BI  

All components work together to build a scalable e-commerce analytics solution.

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
| Security / Secrets | Azure Key Vault |
| Processing | Azure Databricks (PySpark) |
| Warehouse | Azure Synapse Analytics |
| Visualization | Power BI |
| Version Control | GitHub |

---

# 📊 Dataset

I used a small simulated e-commerce dataset containing:

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
I designed the analytical model using a **Star Schema**, which includes three dimension tables dim_customer, dim_product, and dim_date and a single fact_order table .

### ⭐ Dimensions
- `dim_customer`
- `dim_product`
- `dim_date`

### ⭐ Fact Table
- `fact_order` (one row per order item)
  
<img width="1006" height="725" alt="data_modeling" src="https://github.com/user-attachments/assets/7dcc59a3-c253-474e-9ef4-83477c592b94" />



---

# ⚙️ Transformation Pipeline

Inside Databricks, I implemented:

- Secure secret access using **Azure Key Vault** (service principal credentials, storage keys)
- Data type cleaning and standardization  
- Handling of duplicates and missing values  
- Joining all datasets into unified tables  
- Creating derived fields such as total price and discount metrics  
- Generating a reusable date dimension  
- Building the final star schema (dimensions + fact table)


### 🔹 Bronze Layer  
My source data consists of raw CSV files (customers, products, orders, order_items). I used Azure Data Factory to pull these files into the Bronze layer of my Data Lake.

<img width="1455" height="635" alt="adf" src="https://github.com/user-attachments/assets/b0ceaccf-4db4-4646-97d5-76714568de22" />



### 🔹 Silver Layer  

Cleaned + standardized:
- Fixed data types  
- Removed duplicates  
- Derived fields

<img width="1802" height="783" alt="databricks_2" src="https://github.com/user-attachments/assets/84ee2981-ebc3-4075-a713-df1318ca0a61" />

<img width="1685" height="697" alt="databricks_6" src="https://github.com/user-attachments/assets/c503403f-17ef-4394-915b-8b6ba5cf04c0" />


Azure Key Vault : 
<img width="1488" height="507" alt="key_vault" src="https://github.com/user-attachments/assets/7ee116d5-aeaf-4501-a50f-9efbe0b8e87b" />


### 🔹 Gold Layer  
Business-ready:
- Dimensional tables (customer, product, date)
- Fact table (order-level sales metrics)
- Loaded to Synapse for reporting

<img width="1790" height="762" alt="databricks_3" src="https://github.com/user-attachments/assets/90e06cb1-2aa6-4914-8dbc-dc91affeca81" />

All Gold tables were written as optimized Parquet files and exposed to Azure Synapse through **Serverless SQL External Tables** for analytics and reporting.

<img width="1547" height="863" alt="syanpse_3" src="https://github.com/user-attachments/assets/26a5c835-c0bf-4ffa-b7d9-c67bfd48f667" />


---

# 📈 Power BI Dashboard

## ⭐ KPI Cards
- Total Sales  
- Total Orders  
- Total Customers  
- Average Order Value  

### 📊 Visuals
- Sales trend over time (line chart)  
- Revenue by product category (column chart)  
- Top-selling products (bar chart)  
- Customer distribution by country (map/chart)  
- Orders by order status (pie chart)  
- Sales by month (donut chart)

### 🎛 Slicers
- Product category  
- Country  


<img width="1262" height="710" alt="report" src="https://github.com/user-attachments/assets/d908ad7c-d0a4-40a1-ba9b-44fe3646dbd8" />






