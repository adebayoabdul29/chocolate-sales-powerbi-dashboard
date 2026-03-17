#  Chocolate Sales Performance — Power BI Dashboard



##  Project Overview

This project delivers a **single-page interactive Power BI dashboard** for **Chocolate Cacao Company**, transforming raw sales data into executive-ready insights. The dashboard covers 3 years of performance data (2022–2024) across 6 countries, 25 sales representatives, and 22 products — with dynamic year filtering, 3-month moving averages, YoY comparisons, and intelligent performance messaging built entirely in DAX.

---


---

##  Dataset Overview

**Source:** Chocolate Sales Dataset | **Records:** 3,282 transactions | **Period:** 2022 – 2024

| Column | Description |
|---|---|
| `Sales Person` | Name of the sales representative |
| `Country` | Country of the sale (UK, India, Australia, New Zealand, USA, Canada) |
| `Product` | Name of the chocolate product sold |
| `Date` | Date of the transaction |
| `Amount` | Revenue generated from the transaction ($) |
| `Boxes Shipped` | Number of boxes shipped per transaction |

### Data Model
A **Calendar table** was created and linked to the sales table via a one-to-many relationship on the `Date` field, enabling time intelligence calculations.

| Calendar Table | Description |
|---|---|
| `Date` | Full date |
| `Month Name` | Month label |
| `Month Number` | Numeric month (1–12) |
| `Quarter` | Quarter (Q1–Q4) |
| `Year` | Year (2022, 2023, 2024) |

---

##  Dashboard Features

### KPI Cards (Top Row)
| KPI | 2022 | 2023 | 2024 | All Years |
|---|---|---|---|---|
| **Total Revenue** | $6.18M | $6.64M | $6.96M | **$19.79M** |
| **Total Orders** | 1K | 1K | 1K | **3K** |
| **Total Quantity Sold** | 177K | 181K | 182K | **540K** |
| **Average Order Value** | $5.65K | $6.07K | $6.37K | **$6.03K** |
| **YoY Growth %** | — | 7.44% | 4.83% | **54.30%** |

### Visuals
-  **Revenue Trend Line Chart** — Monthly Total Revenue with 3-Month Moving Average overlay
-  **Product Performance Table** — Product, Total Revenue, YoY Sales Growth %, Country, Top 5 Flag
-  **Decomposition Tree** — Revenue broken down by Sales Person → Country → Product
-  **Dynamic Performance Message** — Auto-generated insight text based on YoY performance
-  **Interactive Filters** — Country slicer, Year slicer (2022 / 2023 / 2024), Product slicer

---

##  DAX Measures Used

| Measure | Purpose |
|---|---|
| `Total Revenue` | Sum of all sales amounts |
| `Total Sales` | Total transaction value |
| `Total Orders` | Count of all transactions |
| `Total Quantity Sold` | Sum of boxes shipped |
| `Average Order Value` | Revenue per order |
| `Average Sales` | Mean sales value |
| `Average Monthly Boxes` | Average boxes shipped per month |
| `Cy_revenue` | Current year revenue |
| `Py_revenue` | Previous year revenue |
| `Last Year Sales` | Revenue in the prior year |
| `Last Year Orders` | Order count in prior year |
| `Last Year Quantity` | Quantity in prior year |
| `Last Year AOV` | Average order value in prior year |
| `Last Year YoY` | YoY value in prior year |
| `YoY %` | Year-over-year revenue growth percentage |
| `YoY Display` | Formatted YoY display with arrow indicators |
| `YoY Sales Growth %` | Product-level YoY growth rate |
| `YoYAOV %` | YoY growth in average order value |
| `YoYAOV Display` | Formatted AOV YoY display |
| `YoYO %` | YoY growth in order count |
| `YoYO Display` | Formatted orders YoY display |
| `YoYQ %` | YoY growth in quantity sold |
| `YoYQ Display` | Formatted quantity YoY display |
| `3 Month Moving Average` | Rolling 3-month revenue average |
| `MoM Sales Difference` | Month-over-month revenue change |
| `% Growth_Rate` | Overall growth rate percentage |
| `Best Sales Person Name` | Dynamic top performer name |
| `Performance Color` | Conditional colour formatting for growth |
| `Product Performance Message` | Dynamic insight message based on YoY |
| `Top 5 Product Flag` | Flags whether a product is in the top 5 |

---

##  Key Findings

### Overall Performance (2022–2024)
| Metric | Value |
|---|---|
| **Total Revenue** | $19,791,572 |
| **Total Orders** | 3,282 |
| **Total Boxes Shipped** | 540,437 |
| **Average Order Value** | $6,030 |
| **Overall Growth (vs LY)** | +54.3% |

---

###  Year-on-Year Revenue Growth
| Year | Revenue | YoY Growth |
|---|---|---|
| 2022 | $6,183,625 | — |
| 2023 | $6,643,378 | **+7.44%** |
| 2024 | $6,964,569 | **+4.83%** |

> Revenue has grown consistently every year — with 2023 showing the strongest single-year jump at 7.44%.

---

###  Revenue by Country
| Country | Total Revenue |
|---|---|
| **Australia** | $3,646,444 |
| **UK** | $3,365,389 |
| **India** | $3,343,731 |
| **USA** | $3,313,858 |
| **Canada** | $3,078,496 |
| **New Zealand** | $3,043,654 |

> Revenue is remarkably well-balanced across all 6 countries — no single market dominates, reducing geographic concentration risk.

---

###  Top 5 Sales Representatives
| Rank | Sales Person | Total Revenue |
|---|---|---|
| 1 | **Dennison Crosswaite** | $931,850 |
| 2 | **Beverie Moffet** | $892,421 |
| 3 | **Kaine Padly** | $849,063 |
| 4 | Ches Bonnell | $1,022,600* |
| 5 | Oby Sorrel | $1,017,204* |

> *Based on full dataset analysis. Dennison Crosswaite consistently leads across all three years per the dashboard decomposition tree.

---

###  Top 10 Products by Revenue
| Rank | Product | Total Revenue |
|---|---|---|
| 1 | **Smooth Sliky Salty** | $1,120,201 |
| 2 | 50% Dark Bites | $1,087,659 |
| 3 | White Choc | $1,054,257 |
| 4 | Peanut Butter Cubes | $1,036,591 |
| 5 | Eclairs | $996,948 |
| 6 | 99% Dark & Pure | $960,033 |
| 7 | 85% Dark Bars | $955,268 |
| 8 | Organic Choco Syrup | $945,346 |
| 9 | Spicy Special Slims | $938,132 |
| 10 | Mint Chip Choco | $904,990 |

---

##  Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Dashboard creation, DAX measures, visuals |
| **DAX** | 30+ custom measures for KPIs, YoY, moving averages, and dynamic text |
| **Power Query (M Language)** | Data cleaning and Calendar table creation |
| **CSV (Raw Data)** | Source dataset |

---

