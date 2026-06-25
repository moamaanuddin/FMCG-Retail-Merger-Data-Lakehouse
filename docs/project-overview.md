<div align="center">

# 🚀 Project Overview

### FMCG Retail Merger Data Lakehouse

*A modern Lakehouse solution for post-acquisition enterprise data consolidation.*

</div>

---

## 📌 Introduction

**FMCG Retail Merger Data Lakehouse** is an end-to-end Data Engineering project that simulates a real-world post-acquisition data integration scenario in the Fast-Moving Consumer Goods (FMCG) industry.

The project demonstrates how two organizations with different data architectures, reporting granularities, and business rules can be integrated into a unified analytical platform using the **Databricks Lakehouse Platform**.

The final solution delivers a centralized **single source of truth** that powers enterprise dashboards and AI-assisted analytics.

---

<div align="center">

## 🏗 Solution Architecture

> Replace with `architecture/solution_architecture.png`

</div>

---

## 🎯 Project Objectives

The project was designed to achieve the following objectives:

* Consolidate data from two organizations after an acquisition.
* Standardize inconsistent schemas and business rules.
* Harmonize monthly and daily reporting structures.
* Build a scalable ETL pipeline using the Medallion Architecture.
* Produce business-ready Gold layer datasets.
* Enable enterprise dashboards and AI-powered analytics.

---

## ⚙️ Architecture Overview

The solution follows the **Medallion Architecture**, where data progresses through multiple refinement stages before becoming available for business consumption.

```text
Company A (Monthly Data)
                │
                │
Company B (Daily Data)
                │
                ▼
         Amazon S3 Landing Zone
                │
                ▼
           Bronze Layer
         Raw Delta Tables
                │
                ▼
           Silver Layer
 Data Cleansing & Standardization
                │
                ▼
            Gold Layer
 Enterprise Analytical Model
                │
      ┌─────────┴─────────┐
      ▼                   ▼
 Databricks Dashboard   Databricks Genie
```

---

## 🏛 Medallion Architecture

### 🥉 Bronze Layer

The Bronze layer ingests raw datasets from both organizations without applying business transformations.

**Responsibilities**

* Raw data ingestion
* Historical data preservation
* Source traceability
* Delta table creation

---

### 🥈 Silver Layer

The Silver layer transforms raw datasets into standardized, high-quality business entities.

**Responsibilities**

* Schema standardization
* Data cleansing
* Duplicate removal
* Business rule implementation
* Daily-to-monthly harmonization

---

### 🥇 Gold Layer

The Gold layer contains consolidated analytical datasets optimized for reporting and business intelligence.

**Responsibilities**

* Dimension table creation
* Fact table generation
* Enterprise analytical views
* Dashboard-ready datasets
* AI-ready datasets for Databricks Genie

---

## 🛠 Technology Stack

| Category          | Technology             |
| ----------------- | ---------------------- |
| Platform          | Databricks             |
| Programming       | Python                 |
| Processing Engine | Apache Spark           |
| Query Language    | Spark SQL              |
| Storage           | Amazon S3              |
| Storage Format    | Delta Lake             |
| Governance        | Unity Catalog          |
| Architecture      | Medallion Architecture |
| Visualization     | Databricks Dashboards  |
| AI Analytics      | Databricks Genie       |

---

## 📂 Project Workflow

```text
Raw Parent Company Data
            │
Raw Child Company Data
            │
            ▼
     Amazon S3 Landing
            │
            ▼
        Bronze Layer
            │
            ▼
        Silver Layer
            │
            ▼
         Gold Layer
            │
            ▼
 Enterprise Analytics
      │            │
      ▼            ▼
 Dashboards     Genie
```

---

## ✨ Key Features

* End-to-end ETL pipeline built on Databricks
* Enterprise Lakehouse Architecture
* Parent and Child company data consolidation
* Schema standardization across organizations
* Daily and monthly data harmonization
* Gold layer dimensional modeling
* Interactive business dashboards
* AI-powered analytics with Databricks Genie
* Delta Lake implementation
* Unity Catalog governance

---

## 📈 Business Value

The completed solution enables organizations to transition from isolated reporting systems to a centralized analytics platform.

### Business Outcomes

* 📊 Unified enterprise dashboards
* 📈 Consistent KPI reporting
* 👥 Consolidated customer insights
* 📦 Integrated product analytics
* 💰 Standardized pricing analysis
* 🚀 Faster business decision-making
* 🤖 Natural language analytics with Databricks Genie

---

<div align="center">

## 🎯 Project Outcome

</div>

By integrating heterogeneous datasets into a unified Lakehouse architecture, this project demonstrates how modern Data Engineering practices can simplify post-acquisition data consolidation while delivering scalable, governed, and analytics-ready datasets for enterprise reporting and AI-driven insights.
