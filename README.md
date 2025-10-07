# Modeling-DWH-for-Bookstores_-Using-SSIS
 Designed and developed scalable Data Warehouses, optimized data integration pipelines, and enabled robust reporting and  analytical capabilities.
📚 Gravity Bookstore Data Warehouse Project
📌 Project Overview

This project involves designing and implementing a Data Warehouse (DWH) for a fictional company called Gravity Bookstore.
The goal was to model, build, and integrate a complete analytical environment that captures data about books, authors, customers, sales, and shipping from a transactional database and transforms it into a dimensional model suitable for business intelligence analysis.

The solution includes ETL (SSIS) pipelines for data integration, dimensional modeling (SQL Server), and OLAP cube design (SSAS) for advanced analytics and reporting.

⚙️ Tools & Technologies

Microsoft SQL Server (Database Engine)

SQL Server Integration Services (SSIS) – for ETL data pipelines

SQL Server Analysis Services (SSAS) – for multidimensional OLAP cube design

SQL (DDL, DML) – for modeling and integrity constraints

Excel / Power BI – for validating data outputs (optional check)

📂 Repository Structure

📁 Documentation/

Contains the ERD diagrams, DWH schema screenshots, and integrity check scripts.

Includes mapping sheets and the final architecture overview.

📁 DWH Scripts/

SQL DDL statements for creating all dimension and fact tables in gravity_books_dwh.

📁 SSIS Project/

The ETL workflow that extracts data from the transactional database gravity_books, transforms it, and loads it into the DWH.

📁 SSAS Project/

The OLAP cube design and cube browsing outputs (dimensions, measures, KPIs).

🧩 Data Modeling

The data warehouse was modeled using a Star Schema approach to simplify querying and improve performance for analytics.

Rationale

A star schema was chosen because it:

Reduces query complexity.

Enhances performance for aggregations and reporting.

Provides a clear separation between facts (measurable events) and dimensions (descriptive context).

🗂️ Dimensional Model Components
🧾 Dimension Tables

Dim_Author – Stores author information with surrogate and business keys.

Dim_Book – Includes book details, publication info, language, and publisher data.

Dim_Customer – Contains customer personal and address details.

Dim_Book_Author – Handles the many-to-many relationship between books and authors.

Dim_Address – Stores detailed address hierarchy and country information.

Dim_Customer_Order – Represents order-related metadata and status information.

Dim_Date – A full calendar dimension for tracking historical changes.

Dim_Time – Provides hourly granularity for time-based analysis.

Each dimension includes:

Surrogate Key (SK)

Business Key (BK)

Start/End Date for historical tracking (SCD Type 2 logic)

is_current flag for active records

ssc column for system consistency tracking

📊 Fact Table – Fact_Book

The Fact_Book table captures the measurable business events related to book sales, including:

Order details (orderID_FK, lineID_FK)

Customer and book references

Shipping and order status

Date and time keys (Date_ID_SK_FK, TimeSK_FK)

Measures:

price (sales revenue)

cost (shipping or operational cost)

🔍 Data Integrity & Validation

Data consistency between facts and dimensions was maintained using:

Foreign key constraints between fact and dimension tables.

SQL scripts to validate orphan records and ensure referential integrity.

Custom checks in SSIS to handle null or duplicate business keys.

⚙️ ETL Process (SSIS)

Designed and implemented an ETL workflow that:

Extracts data from the transactional database (gravity_books).

Transforms it by cleaning, renaming, and applying surrogate key logic.

Loads it into the target DWH (gravity_books_dwh) following SCD Type 2 design for tracking historical changes.

ETL workflows handle:

Incremental loads

Duplicate record detection

Error logging and validation

📦 OLAP Cube (SSAS)

A multidimensional cube was built to enable advanced data exploration, including:

Dimensions: Book, Author, Customer, Date, Time, and Shipping.

Measures: Revenue, Cost, Order Count.

KPI examples:

Profit Margin = (Revenue - Cost) / Revenue

Average Lead Time per Order

Total Books Sold per Author

The cube allows slicing and dicing by date, author, publisher, or region for interactive business analysis.

📈 Key Deliverables

✅ Fully functional Data Warehouse schema (gravity_books_dwh).

✅ Complete ETL process (SSIS) with validated transformations.

✅ Configured OLAP Cube (SSAS) for analytical reporting.

✅ Mapping Sheet aligning source and target systems.

✅ Screenshots and documentation of every project stage.

🎯 Project Purpose

This project demonstrates my ability to:

Model and implement a dimensional data warehouse from a transactional source.

Design and develop ETL pipelines using SSIS.

Build and analyze OLAP cubes in SSAS.

Apply best practices for data quality, referential integrity, and performance optimization.

Author

Fatma Hamed Ibrahim Morsi
Data Engineer | SQL & ETL Developer
Passionate about transforming raw data into structured, insightful analytical systems.
