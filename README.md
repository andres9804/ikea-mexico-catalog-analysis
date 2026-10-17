# ikea-mexico-catalog-analysis

<img width="1424" height="802" alt="dashboard_preview" src="https://github.com/user-attachments/assets/3c5b20a2-4bde-4da3-a93e-1eeacb68d331" />

## Project Overview
This project consists of an end-to-end analysis about a product catalog for IKEA Mexico, designed from an E-commerce Operations perspective.

The main objective is to transform a raw dataset into an analytic tool for **Power BI**, allowing to evaluate price health, product distribution and online availability of products.

---

## Tools
* **Python and Pandas:** Data profiling, data type normalizations and memory optimization in ETL pipeline.
* **Power BI Desktop:** Executive interface design, data modeling and interactive visualization.

--- 

## Project Phases
### 1. Data Auditing and Profiling (`docs/01_data_audit_report.md`)
* Initial evaluation for dataset quality (`data/raw/IKEA_product_catalog_MX.csv`)
* Detection of null data, duplicates and data consistency in critical columns.

### 2. ETL Pipeline and Normalization (`docs/02_etl_transformations.md`)
* Null values normalization.
* Explicit data types recast achieving a ~13% memory usage reduction.
* Dropping of redundant columns.

### 3. Dashboard and Business Brief (`docs/03_dashboard_brief.md`)
* Target audience definition.
* Definition of the main KPIs and visual architecture.

## Key Findings
* **Most products are accessible:** Almost the entire catalog is concentrated between $0 and $10,000 MXN with a customer rating from 4.68 to 5.
* **Good online availability:** 78% of the catalog products are available to buy via the website.
* **Most expensive products also satisfy the customer:** Most expensive products (between $40,000 and $80,000) represent a small volume of sales, but keep a high rating score. This could mean that customers feel that quality justifies the price.
