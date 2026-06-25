# 🏢 Business Problem

## Overview

In the **Fast-Moving Consumer Goods (FMCG)** industry, mergers and acquisitions often introduce significant data integration challenges. This project simulates a real-world scenario where **Company A** acquires **Company B**, requiring both organizations' operational data to be consolidated into a single enterprise analytics platform.

Although both companies operate in the same business domain, they maintain **different data architectures, reporting standards, and business rules**, making direct integration impossible.

The objective is to build a modern Lakehouse solution that transforms heterogeneous datasets into a **single source of truth** for reporting and decision-making.

---

# 📈 Business Scenario

```text
                    BEFORE ACQUISITION

        ┌──────────────────────┐      ┌──────────────────────┐
        │      Company A       │      │      Company B       │
        │                      │      │                      │
        │  Monthly Sales Data  │      │   Daily Order Data   │
        │  Monthly Pricing     │      │  Daily Transactions  │
        │  Independent BI      │      │  Independent BI      │
        └──────────────────────┘      └──────────────────────┘


                     Company A acquires Company B
                               │
                               ▼


                     AFTER ACQUISITION

                ❌ Different Data Granularity
                ❌ Different Data Models
                ❌ Different Business Rules
                ❌ Separate Dashboards
                ❌ No Enterprise Reporting
```

---

# 🚧 Challenges

## 📅 Different Reporting Granularity

The most significant challenge was the difference in how business data was stored.

| Company A         | Company B                   |
| ----------------- | --------------------------- |
| Monthly Sales     | Daily Orders                |
| Monthly Pricing   | Daily Transactions          |
| Monthly Reporting | Transaction-Level Reporting |

This difference made it impossible to generate unified KPIs directly from the source systems.

---

## 🧩 Inconsistent Data Models

Both organizations used different structures to represent the same business entities.

```text
Company A                     Company B
───────────────              ───────────────

Customer Code                Customer ID

Product Code                 Product ID

Monthly Sales                Daily Orders

Pricing by Month             Transaction Pricing
```

Additional inconsistencies included:

* Different customer identifiers
* Different product hierarchies
* Different pricing structures
* Different naming conventions
* Different reporting standards

---

## 📊 Fragmented Business Intelligence

Prior to consolidation, each company maintained its own reporting environment.

```text
Company A Reports        Company B Reports

Revenue                  Revenue

Customers                Orders

Products                 Inventory
```

As a result:

* No consolidated revenue reporting
* No unified customer analytics
* No enterprise-wide product insights
* Multiple versions of business KPIs
* No single source of truth

---

# 🎯 Project Objective

Develop an end-to-end **Lakehouse-based Data Engineering solution** capable of integrating data from both organizations into a unified analytical platform.

The solution should:

* ✅ Ingest datasets from both companies
* ✅ Standardize schemas and business rules
* ✅ Harmonize monthly and daily reporting structures
* ✅ Consolidate child company data into the parent company's analytical model
* ✅ Produce enterprise-ready Gold datasets
* ✅ Enable unified dashboards and AI-powered analytics

---

# 🏗 Solution Strategy

The solution follows the **Medallion Architecture** implemented on **Databricks**.

```text
                     Company A
                  (Monthly Data)
                         │
                         │
                         ▼

                 Amazon S3 Landing Zone

                         ▲
                         │

                     Company B
                   (Daily Data)

                         │
                         ▼

              ┌───────────────────────┐
              │     Bronze Layer      │
              │  Raw Source Data      │
              └───────────────────────┘
                         │
                         ▼
              ┌───────────────────────┐
              │     Silver Layer      │
              │ • Data Cleansing      │
              │ • Standardization     │
              │ • Schema Mapping      │
              │ • Data Harmonization  │
              └───────────────────────┘
                         │
                         ▼
              ┌───────────────────────┐
              │      Gold Layer       │
              │ Unified Enterprise    │
              │ Analytical Model      │
              └───────────────────────┘
                         │
                         ▼
           📊 Dashboards        🤖 Databricks Genie
```

---

# 💡 Business Value

After implementation, the organization gains a centralized analytics platform capable of supporting enterprise-wide reporting.

### The solution provides:

* 📊 Unified enterprise dashboards
* 📈 Consistent revenue reporting
* 👥 Consolidated customer analytics
* 🛒 Unified product analytics
* 💰 Standardized pricing insights
* 📦 Integrated sales and inventory reporting
* 🤖 Natural language analytics through Databricks Genie

---

# 🎯 Expected Outcome

```text
                 BEFORE

 Company A Reports   +   Company B Reports

                ↓

     Multiple Versions of Truth



                  AFTER

        Unified Gold Layer

                │

      Enterprise Dashboards

                │

      Databricks Genie

                │

      ✅ Single Source of Truth
```

---

## Key Takeaway

This project demonstrates how a modern **Lakehouse architecture** can address the challenges of post-acquisition data integration by consolidating heterogeneous data sources into a unified analytical platform. By standardizing schemas, harmonizing different reporting granularities, and building enterprise-ready Gold datasets, the solution delivers a scalable **single source of truth** that supports business intelligence, executive reporting, and AI-powered analytics.
