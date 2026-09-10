# Retail Sales Insights — 2023

## Scope

This analysis covers 998 transactions recorded in 2023. All findings below use all product categories and genders, with dashboard slicers cleared. Two transactions dated January 1, 2024 remain in the prepared dataset but are excluded from this reporting period.

Currency has not been verified, so monetary figures are presented without a currency symbol. Results were transcribed from the project’s Excel PivotTables and dashboard screenshots.

## Performance Summary

| Metric | Result |
|---|---:|
| Total revenue | 454,470 |
| Transactions | 998 |
| Units sold | 2,510 |
| Average transaction value | 455.38 |

Average transaction value equals total revenue divided by transaction count. Each transaction has a unique Transaction ID.

## 1. Category Demand and Revenue

| Category | Units sold | Revenue |
|---|---:|---:|
| Beauty | 768 | 142,015 |
| Clothing | 894 | 155,580 |
| Electronics | 848 | 156,875 |
| **Total** | **2,510** | **454,470** |

**Finding:** Clothing leads in units sold, while Electronics leads in revenue. Electronics generated 1,295 more revenue than Clothing despite selling 46 fewer units.

**Recommendation:** Review both unit demand and revenue when planning category inventory. Investigate product mix and price differences before deciding where to allocate additional stock. Exact reorder quantities require inventory and supplier lead-time data.

## 2. Monthly Sales Patterns

| Month | Revenue | Units sold |
|---|---:|---:|
| January | 35,450 | 195 |
| February | 44,060 | 214 |
| March | 28,990 | 194 |
| April | 33,870 | 214 |
| May | 53,150 | 259 |
| June | 36,715 | 197 |
| July | 35,465 | 176 |
| August | 36,960 | 227 |
| September | 23,620 | 170 |
| October | 46,580 | 252 |
| November | 34,920 | 205 |
| December | 44,690 | 207 |
| **Total** | **454,470** | **2,510** |

**Finding:** May has the highest revenue and unit sales. September has the lowest revenue and unit sales within 2023.

**Recommendation:** Investigate category-level demand around May and September. Compare additional years before treating this pattern as recurring seasonality or using it to set staffing and inventory plans.

The prepared dataset contains only two January 2024 transactions, both dated January 1, totaling 1,530 revenue and four units. These records do not establish full-month performance and should not be compared with December as evidence of a monthly sales decline.

## 3. Age Group Purchasing Patterns

| Age group | Revenue | Average transaction value |
|---|---:|---:|
| Under 30 | 123,155 | 490.66 |
| 30–44 | 143,920 | 468.79 |
| 45–59 | 142,580 | 438.71 |
| 60+ | 44,815 | 389.70 |

**Finding:** The 30–44 group contributes the most revenue, while the Under 30 group has the highest average transaction value. These are different measures: total revenue also depends on transaction volume.

**Recommendation:** Examine category mix and transaction counts within each group. Use these patterns to formulate small product-bundle tests, then measure their results rather than assuming that higher observed spending proves a promotion will work.

## 4. Revenue by Category and Gender

| Category | Female | Male | Total |
|---|---:|---:|---:|
| Beauty | 74,830 | 67,185 | 142,015 |
| Clothing | 81,275 | 74,305 | 155,580 |
| Electronics | 76,735 | 80,140 | 156,875 |
| **Total** | **232,840** | **221,630** | **454,470** |

**Finding:** Female customers account for more revenue in Beauty and Clothing; male customers account for more revenue in Electronics.

**Recommendation:** Investigate transaction counts and category mix before interpreting these differences as individual preferences. Total revenue alone does not show which group spends more per customer.

## 5. State Analysis — Simulated Locations

Indian states were randomly assigned to transaction rows for dashboard practice. The state names are real, but their connection to each sale is simulated.

| Rank | State | Revenue |
|---|---|---:|
| 1 | Maharashtra | 26,145 |
| 2 | Gujarat | 21,290 |
| 3 | Madhya Pradesh | 20,660 |
| 4 | Sikkim | 20,520 |
| 5 | Himachal Pradesh | 20,125 |
| 6 | Haryana | 20,030 |
| 7 | Chhattisgarh | 19,715 |
| 8 | Punjab | 19,110 |
| 9 | Rajasthan | 18,835 |
| 10 | Nagaland | 18,475 |
| | **Top 10 total** | **204,905** |

**Finding:** Maharashtra ranks first in this simulated assignment. This is a practice result, not evidence of actual geographic performance.

**Recommendation:** Use verified transaction or store locations before making regional inventory, expansion, or marketing decisions. The Top 10 total is a subset of overall revenue and changes with slicer selections.

## Limitations and Next Steps

- Original dataset source and license still need to be documented.
- Currency is unverified; adding Indian states does not establish that amounts are INR.
- Cost, inventory, lead-time, and campaign data are unavailable. Profitability, stock shortages, and promotion effectiveness cannot be established.
- One year of monthly observations is insufficient to establish recurring seasonality.
- Randomly assigned states must not be interpreted as actual customer residence or store locations.
- Age-group chart summaries use fixed cell references. If a filter removes age-group rows, those references may capture incorrect rows or totals. Replace them with category-keyed lookups before relying on sparse combined filters.
- Further analysis should add verified operational data and evaluate proposed promotions through measured tests.

## Explore the Project

- [Project overview](../README.md)
- [Excel dashboard workbook folder](../dashboard/)
- [Prepared dataset](../data/retail_sales_prepared.csv)
