## E-Commerce Sales Analytics Pipeline

An end-to-end data analytics project for e-commerce sales data using Azure Data Factory, Azure Data Lake Storage, Azure SQL Database, SQL, Python, and Power BI.

This project demonstrates how raw e-commerce sales data can be ingested, stored, cleaned, transformed, modeled, analyzed, and prepared for dashboard reporting.

## Project Overview
E-commerce businesses generate large amounts of sales data from orders, customers, products, regions, cities, and payment channels. Without a proper analytics pipeline, it becomes difficult to track sales performance, identify profitable categories, compare regional sales, and make data-driven business decisions.

This project solves that problem by creating a complete sales analytics pipeline that converts raw CSV data into a structured star schema and business insights.

## Objectives
-Ingest raw e-commerce sales data using Azure Data Factory.
-Store raw data in Azure Data Lake Storage.
-Load sales data into Azure SQL staging tables.
-Clean and transform the dataset using SQL and Python.
-Build a star schema data model for analytics.
-Generate business insights using SQL queries.
-Plan a Power BI dashboard for sales, profit, category, region, and payment analysis.

## Tech Stack

-Azure Data Factory
-Azure Data Lake Storage
-Azure SQL Database / Synapse SQL
-SQL
-Power BI
-CSV Dataset

## Dataset Details
Raw dataset:

```text
dataset/raw/Ecommerce_Sales_Data_2024_2025.csv
```

Dataset summary:

| Metric | Value |
| --- | --- |
| Total Rows | 5000 |
| Total Columns | 14 |
| Date Range | 2023-10-04 to 2025-10-03 |

| Missing Values |  0  |
| Duplicate Order IDs Removed | 0  |
| Total Sales |	 533,666,024.35  |
| Total Profit | 	79,708,734.91  |
Main columns:

``` text Order ID, Order Date, Customer Name, Region, City, Category,
Sub-Category, Product Name, Quantity, Unit Price, Discount,
Sales, Profit, Payment Mode
```

## Pipeline Architecture

```text
Raw E-Commerce CSV Dataset
        |
        v
Azure Data Lake Storage
        |
        v
Azure Data Factory Copy Data Pipeline
        |
        v
Azure SQL Staging Table
        |
        v
SQL Cleaning and Transformation
        |
        v
Star Schema Data Warehouse
        |
        v
Power BI Dashboard
        |
        v
Business Insights
```

## Star Schema Model
The project uses a star schema for efficient analytics and reporting.

Fact table:

```text
fact_sales
```
Dimension tables:

```text
dim_customer
dim_product
dim_location
dim_date
dim_payment
```
The fact table stores measurable values such as sales, profit, quantity, unit price, and discount. Dimension tables store descriptive information such as customer, product, location, date, and payment details.

## Project Structure

```text
E-Commerce Sales Pipeline Project/
|
|-- dataset/
|   |-- raw/
|   |   |-- Ecommerce_Sales_Data_2024_2025.csv
|   |
|   |-- processed/
|       |-- clean_ecommerce_sales.csv
|       |-- fact_sales.csv
|       |-- dim_customer.csv
|       |-- dim_product.csv
|       |-- dim_location.csv
|       |-- dim_date.csv
|       |-- dim_payment.csv
|       |-- data_quality_summary.txt
|
|-- docs/
|   |-- adf_pipeline_steps.md
|   |-- final_report.md
|
|-- powerbi/
|   |-- dashboard_guide.md
|
|-- scripts/
|   |-- build_star_schema.py
|
|-- sql/
|   |-- 01_create_staging_table.sql
|   |-- 02_create_star_schema.sql
|   |-- 03_load_star_schema_from_staging.sql
|   |-- 04_data_quality_checks.sql
|   |-- 05_business_insights_queries.sql
|
|-- README.md
```

## How to Run Local Transformation
Run the Python transformation script from the project root folder:

```text
python scripts\build_star_schema.py
```
This script generates:

**Cleaned sales dataset**
**Fact table CSV**
**Dimension table CSV files**
**Data quality summary**
Generated files are saved in:

```text
dataset/processed/
```

## SQL Execution Order
Run the SQL scripts in the following order:

```text
sql/01_create_staging_table.sql
sql/02_create_star_schema.sql
sql/03_load_star_schema_from_staging.sql
sql/04_data_quality_checks.sql
sql/05_business_insights_queries.sql
```

## Power BI Dashboard Pages
Recommended dashboard pages:

1. **Sales Overview**
2. **Product and Category Analysis**
3. **Regional Performance**
4. **Profit and Discount Analysis**
5. **Payment Mode Analysis**
Recommended KPIs:

**Total Sales**
**Total Profit**
**Total Orders**
**Total Quantity Sold**
**Profit Margin**
**Monthly Sales Trend**
**Sales by Category**
**Sales by Region and City**
**Top Products**
**Payment Mode Distribution**

## Key Business Insights

**Total sales are 533,666,024.35.**
**Total profit is 79,708,734.91.**
**Home Decor, Furniture, Clothing, Books, and Kitchen are among the top sales categories.**
**North region has the highest total sales.**
**Net Banking has the highest sales among payment modes.**
**The dataset supports sales, profit, category, city, region, date, and payment behavior analysis.**
## Future Scope

**Add real-time streaming data ingestion.**
**Connect Power BI directly to Azure SQL for live reporting.**
**Add automated Power BI refresh.**
**Build sales forecasting using machine learning.**
**Add customer segmentation and product recommendation analysis.**
**Include inventory and supply chain analytics.**

## Conclusion

This project demonstrates a complete e-commerce sales analytics pipeline from raw data ingestion to business insight generation. It uses cloud storage, ETL pipeline automation, SQL-based transformation, star schema modeling, and Power BI dashboard planning to support data-driven decision-making.
