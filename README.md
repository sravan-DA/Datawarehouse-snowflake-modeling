# Datawarehouse-snowflake-modeling
Retail Sales data warehouse built in Snowflake using RAW, DIM, and FACT layers with star schema modeling.

## Data Warehouse (Snowflake)

## Overview
This project demonstrates an end-to-end Snowflake data warehouse workflow:
- Load raw sales data (CSV) into a RAW layer
- Build a star schema (DIM + FACT) in an ANALYTICS layer
- Run business-ready analytics queries (monthly revenue, total revenue)

## Architecture
CSV → RAW.SALES → ANALYTICS.DIM_PRODUCTS + ANALYTICS.FACT_SALES → Reporting Queries

## Data Model (Star Schema)
- **DIM_PRODUCTS**: product dimension with a surrogate key (**PRODUCT_ID**)
- **FACT_SALES**: transactional fact table referencing **PRODUCT_ID** and storing metrics

## Project Structure
- `data/sales.csv` — sample input dataset  
- `sql/01_setup.sql` — database, schemas, and warehouse setup  
- `sql/02_raw_tables.sql` — RAW table creation  
- `sql/03_dim_products.sql` — dimension table creation (surrogate key)  
- `sql/04_fact_sales.sql` — fact table creation (joins to dimension)  
- `sql/05_analytics_queries.sql` — reporting queries  

## How to Run (in Snowflake)
1. Run `sql/01_setup.sql`
2. Run `sql/02_raw_tables.sql`
3. Load `data/sales.csv` into `RAW.SALES` using Snowsight **Load Data**
4. Run `sql/03_dim_products.sql`
5. Run `sql/04_fact_sales.sql`
6. Run `sql/05_analytics_queries.sql`

## Skills Demonstrated
- Snowflake fundamentals (DB, schema, warehouse)
- Data ingestion into RAW layer
- Star schema modeling (DIM/FACT)
- Surrogate keys
- SQL transformations and analytics queries
