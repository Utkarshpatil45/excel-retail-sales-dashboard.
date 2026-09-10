# Data Notes

## Dataset and Provenance

The project uses `retail_sales_prepared.csv`, a prepared retail transaction dataset containing 1,000 data rows and 12 columns, plus one header row. Each row represents one transaction with a unique Transaction ID.

- **Original source URL:** Not yet documented.
- **Original author and license:** Not yet verified. Public availability should not be interpreted as permission to redistribute.
- **Prepared file:** [retail_sales_prepared.csv](retail_sales_prepared.csv).
- **Preparation:** Performed in Excel for the Retail Sales Dashboard project.

This is a modified dataset, not an untouched original. Indian state assignments and the Month Start and Age Group helper columns were added during the project. Do not describe the underlying transactions as verified real-world business records without confirming the source.

## Files and Reporting Scope

| Item | Scope |
|---|---|
| Prepared CSV | All 1,000 transactions, including two dated January 1, 2024 |
| Dashboard and published findings | 998 transactions from 2023 |
| State assignments | Simulated locations for practice |
| Monetary unit | Unverified; no currency symbol is assigned |

The two January 2024 transactions were excluded using PivotTable filters rather than deleted from the prepared data:

| Transaction ID | Date | Category | Quantity | Total Amount |
|---|---|---|---:|---:|
| 650 | 2024-01-01 | Electronics | 1 | 30 |
| 211 | 2024-01-01 | Beauty | 3 | 1,500 |

Both records occur on January 1. They do not establish complete January coverage and should not be interpreted as a full-month sales decline relative to December.

## Data Dictionary

| Column | Meaning | Interpretation / format |
|---|---|---|
| Transaction ID | Identifier for a transaction | Unique in the project checks; count IDs rather than sum them |
| Date | Transaction date | CSV uses day-month-year, for example `24-11-2023` |
| Customer ID | Customer identifier | Text such as `CUST001`; do not assume customer count equals transaction count |
| Gender | Gender label supplied in the dataset | Observed labels are Female and Male |
| Age | Age supplied for the customer | Numeric years; source accuracy is unverified |
| State | Randomly assigned Indian state | Simulated; not verified customer residence, store location, or shipping destination |
| Product Category | Transaction category | Beauty, Clothing, or Electronics |
| Quantity | Units purchased | Numeric unit count |
| Price per Unit | Recorded unit price | Monetary unit is unverified |
| Total Amount | Recorded transaction sales amount | Checked against Quantity × Price per Unit |
| Month Start | Derived month grouping | Excel holds the first day of the month; exported CSV displays text such as `Nov 2023` |
| Age Group | Derived age band | Under 30, 30–44, 45–59, or 60+ |

The Age Group CSV labels use ordinary hyphens (`30-44` and `45-59`).

## Preparation Steps

1. Preserved transaction data in the workbook and created a working data sheet.
2. Converted the working range into an Excel Table.
3. Added 1,000 randomly generated Indian state entries for geographic visualization practice.
4. Checked for genuinely empty cells using Go To Special → Blanks.
5. Checked Transaction IDs for duplicates using conditional formatting.
6. Compared Total Amount with Quantity × Price per Unit using an Amount Difference helper column.
7. Added Month Start and Age Group helper columns.
8. Built PivotTables, charts, and KPI summaries with January 2024 excluded from the reporting period.
9. Copied the prepared data sheet to a separate workbook and exported it as CSV UTF-8. The dashboard workbook remains in `.xlsx` format.

The Amount Difference helper was used for checking and is not part of the 12-column CSV.

## Derived Fields and Metrics

With the prepared sheet's column arrangement, these formulas were used from row 2:

| Field | Excel formula |
|---|---|
| Amount Difference, temporary | `=J2-H2*I2` |
| Month Start | `=DATE(YEAR(B2),MONTH(B2),1)` |
| Age Group | `=IF(E2<30,"Under 30",IF(E2<45,"30-44",IF(E2<60,"45-59","60+")))` |

Month Start was displayed using `mmm yyyy` in Excel. Age bands are project-defined analytical groupings, not externally validated customer segments. The age formula assumes valid numeric ages; future imports need validation before applying it.

| Metric | Definition |
|---|---|
| Total revenue | Sum of Total Amount within the active reporting filters |
| Transactions | Count of Transaction ID, supported by unique-ID checks |
| Units sold | Sum of Quantity |
| Average transaction value | Total revenue ÷ transaction count; equivalent to the average Total Amount when each row is one transaction |

Revenue is not profit. The dataset does not provide costs, tax treatment, return handling, or discount definitions sufficient to establish net revenue or profitability.

## Validation Evidence and Limits

Checks were performed by the project author in Excel and discussed through screenshots. This document does not claim an independent audit of the complete workbook or CSV.

| Check | Reported or visible outcome | Limit |
|---|---|---|
| Empty-cell search | Excel reported no cells found in the selected range | Does not detect spaces, placeholder strings, or formulas returning empty text |
| Duplicate Transaction IDs | Author reported all IDs unique | Does not establish unique customers |
| Amount reconciliation | Author reported zero differences | No independent row-by-row verification was performed for this document |
| Date storage | `ISNUMBER(B2)` returned TRUE; monthly summaries were produced | The single-cell check does not prove every date is valid |
| CSV export | GitHub showed 1,001 lines and the expected headers and transaction preview | Line count and preview do not validate every record |

### Reconciliation Totals

| Metric | All records | 2023 dashboard |
|---|---:|---:|
| Transactions | 1,000 | 998 |
| Total Amount | 456,000 | 454,470 |
| Quantity | 2,514 | 2,510 |
| Average transaction value | 456.00 | 455.38 |

The 2023 average is rounded to two decimal places. These totals apply with Product Category, Gender, and any State slicers cleared, while retaining the 2023 reporting filter. A Top 10 State PivotTable has a subset total rather than the overall revenue total.

## Simulated State Assignments

State names were sampled independently with replacement from a list of 28 Indian states using a fixed random seed of 42. Union territories were not included. The generated entries were assigned to transaction rows in order.

The distribution was not weighted by population, store presence, market share, or real demand. Repeated Customer IDs, if present, were not used to enforce a consistent location across transactions.

State-level rankings and slicer results describe this random assignment only. They must not be used as evidence for real regional marketing, inventory allocation, or expansion decisions. Use the label **State (Simulated)** in presentation text even where the CSV header remains `State`.

## Importing the CSV

- Import as UTF-8 and comma-delimited text.
- Parse `Date` explicitly as day-month-year to avoid interpreting `05-06-2023` as May 6 instead of June 5.
- Preserve Customer ID as text.
- Import Quantity, Age, Price per Unit, and Total Amount as numeric fields.
- CSV does not preserve Excel formulas, styles, charts, PivotTables, slicers, or typed date metadata.
- Month Start is exported as a month-year display string. Recreate a first-of-month date from Date when chronological sorting or date calculations are required.
- Retain all source rows; apply the 2023 filter in analysis instead of assuming the CSV contains only 2023.

## Workbook Refresh Considerations

After changing or replacing data, refresh PivotTables and verify that the 2023 filters remain applied consistently. Confirm KPI totals before publishing screenshots.

The Age Group chart summary uses positional cell references. If filtering removes a group, those references may pick up another group or a Grand Total. Replace them with category-keyed lookups or another stable summary before relying on sparse combinations of State, Gender, and Product Category filters.

## Related Files

- [Project overview](../README.md)
- [Business insights](../docs/insights.md)
- [Dashboard workbook folder](../dashboard/)
