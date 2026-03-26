# 📊 Customer Segmentation & Revenue Intelligence Analysis
### End-to-End Data Analytics Project · Excel + Power Query + Power Pivot + DAX

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Power Pivot](https://img.shields.io/badge/Tool-Power%20Pivot-F2C811?style=flat&logo=microsoft&logoColor=black)
![DAX](https://img.shields.io/badge/Language-DAX-0078D4?style=flat)
![Power Query](https://img.shields.io/badge/Tool-Power%20Query-742774?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)
![Dataset](https://img.shields.io/badge/Dataset-UCI%20Online%20Retail-blue?style=flat)

---

## 🗂️ Table of Contents

- [Project Overview](#-project-overview)
- [Key Highlights](#-key-highlights)
- [Dashboard Preview](#-dashboard-preview)
- [Business Problem](#-business-problem)
- [Project Objective](#-project-objective)
- [Tools & Technologies](#️-tools--technologies)
- [Analytical Pipeline](#-analytical-pipeline)
- [Dataset Overview](#-dataset-overview)
- [Data Model](#-data-model)
- [DAX Measures](#-dax-measures)
- [Key Performance Indicators](#-key-performance-indicators)
- [Customer Segments](#-customer-segments)
- [Business Insights & Strategic Actions](#-business-insights--strategic-actions)
- [Dashboards](#-dashboards)
- [Workbook Structure](#-workbook-structure)
- [How to Use](#-how-to-use)
- [Author](#-author)

---

## 🏠 Project Overview

| Attribute | Details |
|---|---|
| **Project Type** | End-to-End Data Analytics Project |
| **Dataset** | Online Retail (UCI Machine Learning Repository) |
| **Period** | December 2010 – December 2011 (13 months) |
| **Domain** | UK-based B2C E-commerce |
| **Methodology** | RFM Segmentation (Recency · Frequency · Monetary) |
| **Created by** | Shivanand S Mathapati |

This project performs a full-cycle customer segmentation and revenue intelligence analysis on a UK-based online retail dataset containing **541,909 transactions**. Using **RFM scoring**, customers are classified into five behavioural segments. The analysis uncovers revenue concentration risks, churn patterns, and strategic growth opportunities — all delivered through interactive Excel dashboards built on a **Power Pivot star schema** and driven by **DAX measures**.

---

## 🧠 Key Highlights

- Built end-to-end customer segmentation using RFM methodology
- Designed star schema data model in Power Pivot
- Developed 2 interactive Excel dashboards
- Identified £1.76M revenue at risk
- Generated actionable business strategies for retention & growth

---

## 📸 Dashboard Preview

The workbook contains two fully interactive Excel dashboards designed to analyze customer behavior, revenue performance, and churn risk.

### Dashboard 01 — Segment Performance Dashboard
![Dashboard](images/customer-segment-performance-dashboard.png)

Visual breakdown of segment-level revenue, customer counts, orders, and revenue-at-risk using PivotCharts driven by Power Pivot. Slicers allow filtering by country, segment, and time period.

### Dashboard 02 — Customer Intelligence Dashboard
![Dashboard](images/customer-revenue-intelligence-dashboard.png)

Customer-level scorecard view showing average CLV, recency, purchase frequency, one-time buyer rate, and retention/churn metrics per segment.

---

## 📥 Download Dashboard

Due to file size limitations, two versions are provided:

* 👉 **GitHub Version**: Includes dashboard with pre-loaded data model (refresh disabled)
* 👉 **Full Version (with raw data)**:
  [Download from Google Drive](https://docs.google.com/spreadsheets/d/1bE4_h30jq0SjNlkIJvr7ZfEpHfsC5E4d/edit?usp=sharing&ouid=103795077483112048512&rtpof=true&sd=true)

> ⚠️ Note: The GitHub version does not include the raw dataset. To refresh data, please use the full version.

---

## 💼 Business Problem

The company wants to understand customer behaviour, purchasing patterns, and revenue contribution in order to improve retention and maximise revenue.

Management needs a data-driven solution that answers:

- Which customers generate the most revenue?
- Which customer segments are most valuable?
- Which customers are at risk of churning?
- How frequently do customers purchase?
- How does customer value vary across segments?
- Where do potential growth opportunities exist?

> **Goal:** Identify high-value customers, reduce churn, and enable targeted marketing strategies that improve Customer Lifetime Value (CLV) and overall business performance.

---

## 🎯 Project Objective

Analyse customer transaction data using **RFM (Recency, Frequency, Monetary)** methodology to segment customers based on their purchasing behaviour.

This analysis aims to:

- Identify high-value and low-value customer segments
- Understand customer purchase frequency and recency patterns
- Measure customer lifetime value (CLV) and revenue contribution
- Detect customers at risk of churn
- Enable targeted marketing and retention strategies
- Provide actionable insights that improve customer retention and increase revenue

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Data model host & dashboard canvas |
| **Power Query (M Code)** | ETL — clean, reshape, and enrich raw invoice data |
| **Power Pivot** | Star-schema relational data model (5 tables) |
| **DAX** | Custom measures — CLV, RFM scoring, churn, risk score, etc. |
| **PivotTables** | EDA: segment × country × time analysis |
| **Slicers** | Interactive country, segment, and recency filters |

---

## 🔄 Analytical Pipeline

```
Step 01 │ Data Ingestion    → Power Query · clean & transform raw invoice data (M Code)
Step 02 │ RFM Scoring       → Recency · Frequency · Monetary quintile scoring
Step 03 │ Segmentation      → 5-segment model via DAX rules in Power Pivot
Step 04 │ EDA & Pivots      → Segment × country × time × product analysis
Step 05 │ Dashboards        → Segment Performance Dashboard (charts) + Customer Intelligence Dashboard (customer scorecard)
```

---

## 📦 Dataset Overview

| Attribute | Detail |
|---|---|
| **Source** | UCI Machine Learning Repository — Online Retail Dataset |
| **Period** | December 2010 – December 2011 |
| **Total Rows** | 541,909 raw transactions |
| **Geography** | UK-based e-commerce (international customers included) |

### Column Dictionary

| Column | Description |
|---|---|
| `InvoiceNo` | Order ID — 6-digit number |
| `StockCode` | Product ID — 5-digit number |
| `Description` | Product name |
| `Quantity` | Units purchased per line item |
| `InvoiceDate` | Purchase date & time |
| `UnitPrice` | Price per item (GBP — British Pound Sterling) |
| `CustomerID` | Customer identifier — 5-digit number |
| `Country` | Customer location |

---

## 🧩 Data Model

The workbook uses a **Star Schema** with 5 fully relational tables in Power Pivot (1-to-many relationships):

```
                        ┌─────────────────┐
                        │   Calender      │
                        │ (Date Dimension)│
                        └────────┬────────┘
                                 │
┌───────────────────┐   ┌────────▼────────────────┐   ┌─────────────────┐
│     Country       │   │  Clean_Data_Connection  │   │    Customers    │
│(Geo Dimension)    ├───►    (Fact Table)          ◄───┤ (RFM + Segment) │
└───────────────────┘   └────────┬────────────────┘   └─────────────────┘
                                 │
                        ┌────────▼────────┐
                        │  Recency_Param  │
                        │ (Dynamic Filter)│
                        └─────────────────┘
```

| Table | Role |
|---|---|
| `Clean_Data_Connection` | Fact Table — Invoice-level transaction data |
| `Customers` | Dimension — RFM scores and segment labels |
| `Country` | Dimension — Geographical lookup |
| `Calender` | Dimension — Date, Month, Year hierarchy |
| `Recency_Parameter` | Dynamic recency filter table |

---

## 📐 DAX Measures

Key DAX measures powering the dashboards and KPI sheet:

```dax
-- Total Revenue
Total Revenue = SUMX(Clean_Data_Connection, Clean_Data_Connection[Quantity] * Clean_Data_Connection[UnitPrice])

-- Customer Lifetime Value
CLV = DIVIDE([Total Revenue], [Total Customers])

-- Churn Rate
Churn Rate = DIVIDE([Churn Customers], [Total Customers])

-- Retention Rate
Retention Rate = 1 - [Churn Rate]

-- Revenue At Risk
Revenue At Risk = CALCULATE([Total Revenue], Customers[Segment] IN {"At Risk", "Lost Customers"})

-- Risk Score (Weighted composite)
Risk Score = AVERAGEX(Customers, Customers[Risk_Score])

-- Predicted CLV
Predicted CLV = [Avg Revenue Per Customer] * [Avg Purchase Frequency] * [Avg Customer Lifespan]

-- RFM Segment Assignment (simplified)
Segment =
    IF([R_Score] >= 4 && [F_Score] >= 4 && [M_Score] >= 4, "Champions",
    IF([R_Score] >= 3 && [F_Score] >= 3, "Loyal Customers",
    IF([R_Score] >= 3 && [F_Score] <= 2, "Potential Loyalists",
    IF([R_Score] <= 2 && [F_Score] >= 3, "At Risk",
    "Lost Customers"))))
```

---

## 📊 Key Performance Indicators

| KPI | Value |
|---|---|
| 💰 **Total Revenue** | £8,911,407.90 |
| 👥 **Total Customers** | 4,338 |
| 📦 **Total Orders** | 18,532 |
| ✅ **Active Customers** | 2,889 |
| ❌ **Churned Customers** | 858 |
| 🆕 **New Customers** | 1,493 |
| 📉 **Churn Rate** | 19.78% |
| 📈 **Retention Rate** | 80.22% |
| 🔁 **Repeat Rate** | 65.58% |
| 1️⃣ **One-Time Buyer Rate** | 34.42% |
| 🎯 **Avg Order Value (AOV)** | £480.87 |
| ⏱ **Avg Recency (Days)** | 92 days |
| 💎 **Customer Lifetime Value (CLV)** | £736.00 |
| ⚠️ **Revenue At Risk** | £1,762,560.62 |
| 🦺 **Safe Revenue** | £7,148,847.28 |
| 📊 **Orders per Customer** | 4.27 |
| ⚠️ **Revenue Risk Score** | 2.63 / 10 |

---

## 👥 Customer Segments

Five segments derived from RFM quintile scoring via DAX:

| Segment | Customers | Revenue (£) | Revenue % | Avg CLV (£) | Avg Recency | Retention | Churn | Risk Score |
|---|---|---|---|---|---|---|---|---|
| 🏆 **Champions** | 911 | 5,688,406 | 63.83% | 4,888.40 | 12 days | 100% | 0% | 0.13 |
| 💎 **Loyal Customers** | 707 | 1,207,709 | 13.55% | 986.34 | 34 days | 100% | 0% | 0.37 |
| ⚠️ **At Risk** | 405 | 884,759 | 9.93% | 811.69 | 143 days | 74.57% | 25.43% | 2.72 |
| 🌱 **Potential Loyalists** | 515 | 422,820 | 4.74% | 158.29 | 17 days | 100% | 0% | 1.56 |
| ❌ **Lost Customers** | 1,800 | 707,714 | 7.94% | 39.97 | 165 days | 58.06% | 41.94% | 5.08 |
| **Grand Total** | **4,338** | **8,911,408** | **100%** | **736.00** | **92 days** | **80.22%** | **19.78%** | **2.63** |

---

## 💡 Business Insights & Strategic Actions

| # | Focus Area | Data Finding | Business Insight | Strategic Action |
|---|---|---|---|---|
| 1 | **Revenue Concentration Risk** | Champions (21% of customers) generate 63.83% of total revenue | Business is dangerously dependent on a tiny elite segment | Launch VIP Champions Retention Programme |
| 2 | **Lost Customers Revenue Leak** | 1,800 customers (41.49%) generate only 7.94% of revenue; avg CLV £39.97 | Nearly half the base has disengaged — massive retention failure | Deploy Win-Back Campaign targeting top 300 by historical spend |
| 3 | **Revenue At Risk** | £1.76M flagged at risk — 19.8% of total revenue in jeopardy | Critical financial exposure requiring urgent intervention | Revenue Rescue Task Force with 30-day outreach deadline |
| 4 | **Churn Rate Crisis** | 19.78% overall churn; At Risk 25.43%; Lost Customers 41.94% | ~858 customers lost per year — compounding attrition ahead | Churn Prediction Model using RFM scores with 60-day early flag |
| 5 | **One-Time Buyer Problem** | 34.42% one-time buyer rate; Lost Customers 66.94% | Broken post-purchase experience or inadequate onboarding | First-Purchase Nurture Sequence (Day 3 → Day 7 → Day 14) |
| 6 | **Potential Loyalists Opportunity** | 515 customers, avg recency 17 days, zero revenue at risk | Most recent and engaged non-Champion segment | 90-day Loyalty Conversion Sprint |
| 7 | **CLV Gap** | Champions CLV (£4,888) vs Lost Customers CLV (£39.97) = 122× gap | ROI of retaining one Champion = retaining 16 Lost Customers | CLV-Based Resource Allocation Model |
| 8 | **Frequency as Growth Driver** | Champions avg 11 purchases vs Grand Total of 4 | Frequency is the single strongest differentiator of segment value | Subscription / Auto-Replenishment Model for top SKUs |
| 9 | **UK Revenue Dominance** | UK accounts for £7.31M (82% of revenue) across 3,920 customers | International expansion is an untapped growth vector | Targeted geo-expansion into Netherlands and Ireland |
| 10 | **Three-Horizon Strategy** | £8.91M revenue, 19.78% churn, £1.76M at risk | Strong Champion core offset by structural churn weakness | H1: Defend Champions. H2: Convert Loyalists. H3: Fix Onboarding |

---

## 📁 Workbook Structure

| Sheet | Contents |
|---|---|
| `Raw_Data` | Original 541,909 invoice records |
| `🏠 Project_Overview` | Full project documentation, objectives, and methodology |
| `🔍 EDA` | Exploratory Data Analysis via PivotTables |
| `🧩 Data_Model` | Star schema relationship diagram |
| `🎯 KPI_Analysis` | All KPI cards with values and descriptions |
| `📊 Segment_Performance_Dashboard` | Dashboard 01 — Revenue & segment charts |
| `👥 Customer_Intelligence_Dash` | Dashboard 02 — Customer behaviour scorecard |
| `💡 Business_Insights_&_Actions` | 20 data-driven findings and strategic recommendations |
| `KPI_For_Dashboards` | Back-end KPI values powering dashboard cards |
| `Calender` | Date dimension table (374 rows) |
| `Pivot_For_DashBoard` | Aggregated pivot data feeding dashboard visuals |

---

## 🚀 How to Use

1. **Open** the `.xlsx` file in Microsoft Excel (2016 or later recommended)
2. Navigate to `🏠 Project_Overview` to understand the project context
3. Explore `🎯 KPI_Analysis` for headline metrics
4. Open `📊 Segment_Performance_Dashboard` and use the **Slicers** to filter by country or segment
5. Open `👥 Customer_Intelligence_Dash` for customer-level behavioural metrics
6. Review `💡 Business_Insights_&_Actions` for the full strategic recommendation table
7. Examine `🔍 EDA` for the underlying PivotTable analysis

> **Note:** Enable **Data Connections** and **Power Pivot** when prompted on first open to ensure all DAX measures calculate correctly.

---

## 👤 Author

**Shivanand S Mathapati**
Data Analyst | Excel · Power Query · Power Pivot · DAX · SQL · Python (currently learning)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com)

---

## 📄 License

This project is for portfolio and educational purposes. The dataset is sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail) and is publicly available.

---

*Built with ❤️ using Microsoft Excel · Power Query · Power Pivot · DAX*
