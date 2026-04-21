# Predictive and Prescriptive Analytics Engine for E-Commerce

## Overview

This project presents an end-to-end data engineering and analytics solution built on a Brazilian e-commerce dataset. It demonstrates how raw transactional data can be transformed into a structured data warehouse and leveraged for advanced analytics and business intelligence.

The system integrates ETL pipelines, a PostgreSQL-based warehouse, and Power BI dashboards to support descriptive, predictive, and prescriptive analytics use cases. The primary goal is to enable data-driven decision-making by providing clean, reliable, and query-optimized data.

---

## Data Source

The dataset used in this project is publicly available:

- Brazilian E-Commerce Public Dataset by Olist  
  https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

### Steps to Download Data

1. Visit the dataset link above
2. Download the dataset (ZIP format)
3. Extract files into the `/data` directory of this repository

---

## Project Structure
Predictive_and_Prescriptive_Analytics_Engine/
│
├── data/ # Raw dataset files
├── etl/ # Pentaho ETL jobs and transformations (.ktr, .kjb)
├── sql/ # Schema creation and transformation scripts
├── dashboards/ # Power BI (.pbix) file
└── README.md
---

## Architecture
Raw Data Sources
↓
ETL Pipelines (Pentaho Data Integration)
↓
Data Cleaning and Transformation
↓
PostgreSQL Data Warehouse (Star Schema)
↓
Analytics Layer (SQL + Python)
↓
Power BI Dashboard


---

## Data Warehouse Design

The warehouse is modeled using a star schema to optimize analytical queries.

### Fact Table
- `fact_orders`  
  Contains transactional metrics such as order value, timestamps, and delivery performance.

### Dimension Tables
- `dim_customers`
- `dim_products`
- `dim_sellers`
- `dim_time`
- `dim_geolocation`

This design enables efficient aggregation and slicing across business dimensions.

---

## ETL Pipeline

ETL pipelines are implemented using Pentaho Data Integration.

### Key Responsibilities

- Extract data from CSV files
- Clean and standardize inconsistent records
- Handle missing values and duplicates
- Transform data into dimension and fact tables
- Load processed data into PostgreSQL

---

## Getting Started

### 1. Clone Repository

```bash
git clone https://github.com/kevalrakholiya/Predictive_and_Prescriptive_Analytics_Engine.git
cd Predictive_and_Prescriptive_Analytics_Engine
```

## 2. Set Up Database

- Install PostgreSQL  
- Create a new database  

```sql
CREATE DATABASE ecommerce_dw;
```
- Update database credentials inside ETL configuration files

## 3. Run ETL Pipelines
- Open Pentaho Data Integration (Spoon)
- Load .ktr or .kjb files from /etl directory
- Execute pipelines to populate the warehouse
  
## 4. Launch Dashboard
- Open Power BI Desktop
- Load .pbix file from /dashboards
- Connect to PostgreSQL database
- Refresh data


