<div align="center">

# 📊 Retail Sales Dashboard
### Excel Sales Analysis · 2023

Explore sales trends, category performance, and customer purchasing patterns.

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat-square)
![Year](https://img.shields.io/badge/Analysis-2023-165D7D?style=flat-square)
![Transactions](https://img.shields.io/badge/Transactions-998-165D7D?style=flat-square)

[View Workbook](dashboard/) · [Explore Data](data/) · [Dashboard Preview](#dashboard-preview)

</div>

---

## 🖼️ Dashboard Preview

![Retail Sales Dashboard](screenshots/Screenshot%202026-09-10%20054638.png)

> **Interactive filters:** Product Category and Gender. Download the workbook and open it in Excel to use the slicers.

## 📈 Performance at a Glance

| Total Revenue¹ | Transactions | Units Sold | Average Transaction Value¹ |
|:---:|:---:|:---:|:---:|
| **454,470** | **998** | **2,510** | **455.38** |

¹ Currency is unverified. Results cover 2023 with all slicers cleared.

## 💡 Key Findings

| Business Question | Finding |
|---|---|
| Which category generated the most revenue? | **Electronics — 156,875** |
| Which category sold the most units? | **Clothing — 894 units** |
| Which month had the highest revenue? | **May — 53,150** |
| Which age group generated the most revenue? | **30–44 — 143,920** |
| Which age group had the highest average bill? | **Under 30 — 490.66** |

## 🚀 How to Explore

1. Open the [dashboard folder](dashboard/) and download the Excel workbook.
2. Open the workbook in Microsoft Excel.
3. Visit the **Dashboard** sheet.
4. Use **Product Category** and **Gender** slicers to explore results.
5. Clear both filters to restore the overall 2023 view.

## 📁 Project Files

| Folder | Contents |
|---|---|
| [dashboard](dashboard/) | Excel workbook |
| [data](data/) | Uploaded dataset |
| [screenshots](screenshots/) | Dashboard images |

<details>
<summary><strong>Tools and analysis workflow</strong></summary>

- Excel Tables and formulas
- Blank-cell and duplicate Transaction ID checks
- Verification of Quantity × Price per Unit against Total Amount
- Month Start and Age Group helper columns
- PivotTables, PivotCharts, and connected slicers
- KPI summaries and dashboard formatting

</details>

<details>
<summary><strong>Data scope and limitations</strong></summary>

- Original dataset: **1,000 transactions**.
- Reporting scope: **998 transactions from 2023**.
- Two transactions dated January 1, 2024 remain in the source
  but are excluded from the dashboard's reporting period.
- State locations were randomly assigned for practice.
  Geographic results are simulated.
- Currency has not been verified.
- Cost, inventory, and campaign data are unavailable.
  Profitability, stock shortages, and promotion effectiveness
  cannot be established from this dataset.
- Original dataset source and license are still to be documented.

</details>
