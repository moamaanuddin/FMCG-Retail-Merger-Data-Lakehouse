<div align="center">

# 🚀 Setup Guide

### FMCG Retail Merger Data Lakehouse

*Step-by-step instructions to deploy and execute the complete Lakehouse pipeline using Databricks Free Edition.*

</div>

---

# 📋 Prerequisites

Before running the project, ensure the following prerequisites are available.

| Requirement   | Description            |
| ------------- | ---------------------- |
| Databricks    | Free Edition Workspace |
| Python        | 3.x                    |
| Apache Spark  | Databricks Runtime     |
| Amazon S3     | Source data storage    |
| Unity Catalog | Enabled                |
| Git           | For version control    |

---

# 📂 Repository Structure

```text
fmcg-retail-merger-data-lakehouse/

├── architecture/
│   ├── solution_architecture.png
│   ├── medallion_architecture.png
│   └── dimensional_model.png
│
├── dashboards/
│
├── docs/
│   ├── business-problem.md
│   ├── project-overview.md
│   ├── dimensional-model.md
│   └── setup-guide.md
│
├── genie/
│
├── notebooks/
│   ├── 1_setup/
│   ├── 2_dim_data_processing/
│   └── 3_fact_data_processing/
│
├── sql/
│
├── README.md
└── LICENSE
```

---

<div align="center">

# ⚙️ Environment Setup

</div>

## Step 1 — Clone the Repository

Clone the repository to your local machine.

```bash
git clone https://github.com/<your-username>/fmcg-retail-merger-data-lakehouse.git

cd fmcg-retail-merger-data-lakehouse
```

---

## Step 2 — Configure Amazon S3

Upload the source datasets for both organizations to your Amazon S3 bucket (or another supported cloud storage location).

The project expects datasets for:

* Customers
* Products
* Gross Price
* Orders

These datasets are ingested into the Bronze layer before progressing through the Medallion Architecture.

---

## Step 3 — Configure Databricks

Create the required resources inside your Databricks workspace.

* Unity Catalog
* Schema
* External Location
* Compute Cluster

Ensure your cluster has access to the configured storage location.

---

<div align="center">

# 🏗 Pipeline Execution

</div>

Execute the notebooks sequentially.

```text
1_setup

      │

      ▼

2_dim_data_processing

      │

      ▼

3_fact_data_processing
```

---

# 📁 Stage 1 — Initial Setup

**Directory**

```text
notebooks/1_setup/
```

### Purpose

This stage prepares the project environment.

Tasks performed:

* Create Catalog
* Create Schema
* Configure Storage
* Load Parent Company datasets
* Load Child Company datasets

---

# 📁 Stage 2 — Dimension Processing

**Directory**

```text
notebooks/2_dim_data_processing/
```

### Purpose

This stage standardizes business entities across both organizations.

Dimension tables created:

* dim_customers
* dim_products
* dim_date
* dim_gross_price

Key operations:

* Schema standardization
* Data cleansing
* Duplicate removal
* Business rule implementation
* Parent–Child data harmonization

---

# 📁 Stage 3 — Fact Processing

**Directory**

```text
notebooks/3_fact_data_processing/
```

### Purpose

This stage creates consolidated transactional datasets for analytics.

Objects created:

* fact_orders
* Analytical Views

Key operations:

* Transaction consolidation
* Business metric generation
* Gold layer preparation
* Reporting optimization

---

<div align="center">

# ✅ Validation

</div>

After successful execution, verify that the following Gold Layer objects have been created.

```text
dim_customers

dim_products

dim_date

dim_gross_price

fact_orders

vw_fact_orders_enriched
```

These datasets serve as the foundation for enterprise reporting and analytics.

---

<div align="center">

# 📊 Business Intelligence

</div>

The Gold Layer powers interactive Databricks Dashboards that provide business insights such as:

* Revenue Overview
* Sales Trends
* Top Products
* Top Customers
* Revenue by Channel
* Customer Analytics
* Business KPIs

---

<div align="center">

# 🤖 AI-Powered Analytics

</div>

The consolidated Gold Layer is exposed to **Databricks Genie**, allowing business users to interact with enterprise data using natural language.

### Example Questions

* What is the total revenue this year?
* Show the top 10 products by revenue.
* Which customer generated the highest revenue?
* Show monthly sales trends.
* Compare revenue by sales channel.
* Which products contributed the highest sales?

---

<div align="center">

# 🎯 Expected Outcome

</div>

After successfully executing the pipeline, the project delivers:

* ✅ Unified enterprise data model
* ✅ Standardized Gold Layer datasets
* ✅ Consolidated business reporting
* ✅ Interactive dashboards
* ✅ AI-powered analytics with Databricks Genie
* ✅ A single source of truth for enterprise decision-making

---

<div align="center">

# 🎉 Setup Complete

Your Lakehouse environment is now fully configured and ready to support enterprise analytics across the merged FMCG organization.

The pipeline successfully integrates heterogeneous datasets from both companies into a unified, governed, and analytics-ready platform built on the Databricks Lakehouse architecture.

</div>
