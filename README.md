# Sales & Customer Analytics

**Project Status:** Analysis and documentation completed; upstream dataset provenance and licence remain unverified.

**Primary Tool:** Microsoft Excel

**Supporting Tools:** Git & GitHub

**Dataset:** Retail sales and customer transaction dataset

**Analysis Type:** Sales performance, customer segmentation, product analytics, and regional trend analysis

This project evaluates sales performance and customer behaviour using a retail transaction dataset. The objective is to assess and validate the source data, structure Excel-based analysis, and produce a clear overview of revenue drivers, customer patterns, and business trends that can be communicated through summary reporting and dashboard visuals.

## Project Overview

The analysis focuses on how sales vary by time, region, product category, customer segment, and order behaviour. It combines data profiling, validation, formula development, PivotTable analysis, KPI tracking, and dashboard reporting to produce a practical and evidence-based view of business performance.

The project is designed to answer the following questions:

* Which time periods produce the highest sales volume and revenue?
* Which product categories and sub-categories contribute the most to revenue?
* How do sales vary across regions, states, and customer segments?
* Which customer groups represent the strongest value opportunities?
* What business insights can be supported by the available dataset, and what requires further operational context?

## Business Context

This project supports business analysis and decision-making by turning raw transaction records into interpretable business insight. The dataset contains sales, product, customer, and geographical information needed to understand performance across a retail network.

The aim is to provide a clear and evidence-based understanding of sales trends while maintaining transparency about the limitations of the dataset. It is intended as a practical analytics case study and portfolio project built around real-world retail data structures.

## Dataset Summary

The project uses the dataset in `Data/Raw/train.csv`.

### Dataset Characteristics

* **9,800 transaction records**
* **18 fields**
* **4,922 orders** from **793 customers**
* **1,861 products**
* **3 customer segments**
* **3 product categories** and **17 sub-categories**
* **4 regions** and **49 states**
* **4 ship modes**
* **Country:** United States
* **Order date range:** 2015-01-03 to 2018-12-30
* **Ship date range:** 2015-01-07 to 2019-01-05

### Important Data Notes

* The raw source file is preserved before any cleaning or transformation.
* The cleaned CSV currently matches the raw CSV field-for-field; no source rows or field values were changed. The workbook parses the `DD/MM/YYYY` dates as day-first Excel dates and adds derived fields.
* Eleven missing postal codes are retained because their values cannot be confirmed from the available files.
* No exact duplicate rows were found, and all dates parse with no ship date preceding its order date. Sales values are numeric and non-negative.
* The repository does not record the dataset's upstream provider, source URL, or licence; provenance and reuse permissions remain unverified.
* The source has no quantity, discount, cost, profit, promised delivery date, or delivery confirmation fields. Profitability, unit demand, discount impact, and delivery compliance cannot be assessed.

## Repository Structure

```text
Sales-Customer-Analytics/
│
├── Data/
│   ├── Raw/
│   │   └── train.csv
│   └── Cleaned/
│       └── train_cleaned.csv
│
├── docs/
│   ├── PERSONAL-PROJECT-PROPOSAL.md
│   ├── PERSONAL PROJECT PROPOSAL.odt (pre-existing office-format copy)
│   ├── PROJECT MANAGEMENT TRACKER.odt
│
├── excel/
│   └── sales_customer_analytics_calculations.xlsx
│
├── README.md
└── .git
```

## Project Methodology

The project follows a structured workflow from planning through final review and documentation.

### PM-01 — Project Planning

This stage defines the project aim, objectives, scope, and analytical approach. It identifies the business problem and questions to answer, and sets out the project workflow before data work begins.

**Deliverable:** Approved project proposal and project plan, documented in [PERSONAL-PROJECT-PROPOSAL.md](docs/PERSONAL-PROJECT-PROPOSAL.md).

**Status:** Completed

### PM-02 — Dataset Preparation

This stage reviews the available dataset files and preserves the raw data without modification. The repository does not identify the upstream provider, source URL, or applicable licence, so provenance and usage conditions could not be independently confirmed; this limitation is noted above.

**Deliverable:** Preserved [raw dataset](Data/Raw/train.csv); the source-provenance limitation is summarized above.

**Status:** Completed with provenance limitation noted

### PM-03 — Data Profiling

This stage inspects the dataset's columns, data types, missing values, duplicates, value ranges, and key identifiers to identify quality issues that may affect the analysis.

**Findings:** The source and analysis-input CSVs each have 9,800 records and 18 fields. There are no exact duplicate rows; required identifiers are populated and `Row ID` is unique. The only missing values are 11 blank postal codes, retained without imputation. Sales is numeric and non-negative. Both date fields parse as day-first `DD/MM/YYYY`, and no ship date precedes its order date.

**Status:** Completed

### PM-04 — Data Cleaning

No exact duplicate rows were found and no records were removed. The cleaned CSV is currently field-for-field identical to the raw CSV, including its `DD/MM/YYYY` date strings. The workbook parses both date columns as day-first dates and stores them as Excel dates for analysis. The 11 missing `Postal Code` values are retained because their values cannot be confirmed from the source data.

**Deliverable:** [Analysis input CSV](Data/Cleaned/train_cleaned.csv). It currently matches the raw CSV field-for-field; dates are interpreted as day-first dates in the workbook, where derived analysis fields are added.

**Status:** Completed

### PM-05 — Data Validation

This stage verifies date formats and order, required identifiers, sales values, and record counts in the cleaned dataset against the preserved raw source.

**Validation notes:**

* 9,800 records and 18 fields match the raw source.
* All order and ship date values parse successfully as day-first `DD/MM/YYYY` dates, and no ship date precedes the order date.
* All `Row ID`, `Order ID`, `Customer ID`, and `Product ID` values are populated, and all `Row ID` values are unique.
* All sales values are numeric and non-negative, ranging from 0.444 to 22,638.48.
* The 11 missing `Postal Code` values remain blank because they were not confirmed in the source data.

**Status:** Completed

### PM-06 — Formula Development

This stage creates the required analytical calculations that support the project questions and downstream reporting. The `Calculations` and `SalesData` worksheets hold the parsed dates, derived year and month fields, shipping duration, and source sales values used by downstream summaries.

**Method:** The workbook parses dates as day-first Excel dates, derives order year/month and calendar shipping duration, and uses sales sums for revenue summaries. Transaction counts are source-row counts; order counts use distinct Order IDs. KPIs, PivotTables, and dashboard summaries are built from the workbook's `SalesDataTable`.

**Deliverable:** [Excel calculations workbook](excel/sales_customer_analytics_calculations.xlsx) with the calculation logic and source data.

**Status:** Completed

### PM-07 — Sales and Customer Analysis

This stage analyses sales by time, product, geography, segment, and customer using the validated transaction data and calculation sheet. The focus is to identify revenue patterns, category performance, regional differences, and the highest-value customer groups.

**Analysis worksheets in the Excel workbook:**

* `Analysis_Summary`: headline KPIs and key findings.
* `Analysis_Time`: annual totals, year-over-year change, monthly sales by year, and month-of-year comparisons.
* `Analysis_Product`: category and sub-category sales plus the top 20 products.
* `Analysis_Geography`: regional and state sales.
* `Analysis_Segment`: sales by customer segment.
* `Analysis_Customer`: the top 20 and full customer ranking, with sales, sales share, transaction count, and distinct order count.
* `SalesData`: the 9,800 source transaction rows and derived year, month, and shipping-day fields.

**Summary findings:**

* Total sales are 2,261,536.78 across 9,800 transaction rows, 4,922 distinct orders, and 793 customers.
* Highest annual sales occur in 2018 at 722,052.02.
* Technology is the highest revenue category at 827,455.87.
* West is the highest revenue region at 710,219.68.
* Consumer is the largest segment at 1,148,060.53 in total sales.
* Top customer by sales is Sean Miller (SM-20320) at 25,043.05.

The cleaned CSV stores dates as `DD/MM/YYYY`; the workbook parses them as day-first dates and stores them as Excel dates before grouping by year and month. Transaction counts are source-row counts, not order counts. The source does not contain profit, discount, or quantity fields.

Average order value is total sales divided by distinct orders. Repeat customers have at least two distinct orders during this dataset period; this is not a retention or churn measure. Sales per customer is not customer lifetime value, and shipping duration is not delivery compliance. Results are descriptive of the provided data, not causal or forecast conclusions.

**Deliverable:** [Excel workbook](excel/sales_customer_analytics_calculations.xlsx) with the calculations, source data, analysis worksheets, and summary tables for sales and customer review.

**Status:** Completed

### PM-08 — PivotTable Analysis

This stage builds and checks native Excel PivotTables from the transaction data and calculated time and shipping fields in `SalesDataTable`.

**PivotTable worksheets:**

* `Pivot_Time`: sales by order year and month number.
* `Pivot_Product`: sales by category and sub-category.
* `Pivot_Geography`: sales by region and state.
* `Pivot_Segment`: sales by customer segment.
* `Pivot_Customer`: sales by customer name and ID, sorted from highest to lowest sales.
* `Pivot_Shipping`: sales, average shipping days, and transaction count by ship mode.

These are native Excel PivotTables sharing a pivot cache sourced from the 9,800 rows in the `SalesDataTable` on the `SalesData` worksheet. They include total sales and transaction counts; the shipping PivotTable also reports average shipping duration. The cache is set to refresh when the workbook opens.

**Validation notes:**

* Each PivotTable uses the same 9,800 source records and reconciles to total sales of 2,261,536.78 and 9,800 transactions.
* Technology leads category sales at 827,455.87; West leads regional sales at 710,219.68; Consumer leads segment sales at 1,148,060.53.
* The customer PivotTable is sorted by sales, with Sean Miller (SM-20320) first at 25,043.05.

**Deliverable:** [Excel workbook](excel/sales_customer_analytics_calculations.xlsx) with the source table and six native PivotTable worksheets.

**Status:** Completed

### PM-09 — KPI Development

This stage calculates supported sales, order, customer, and shipping KPIs and validates them against the PM-07 analysis and source data.

**KPI summary worksheet:** `KPI_Summary` includes total sales, distinct orders, average order value, transaction count, sales per transaction, distinct customers, period sales per customer, repeat customers and repeat-customer rate, average shipping days, 2018 sales growth versus 2017, top-ten customer sales share, and Consumer segment sales share. Each KPI includes its definition and source.

**Validation:** Workbook formula checks pass for total sales (2,261,536.78), transaction rows (9,800), distinct orders (4,922), distinct customers (793), and 2018 sales growth (20.3% versus 2017). Other calculated results include an average order value of 459.48, 780 repeat customers (98.4%), average shipping duration of 3.96 days, and a top-ten customer sales share of 6.8%.

Average sales per customer describes this dataset period and is not customer lifetime value. Repeat-customer rate is based on customers with at least two distinct orders and is not a retention or churn measure. Shipping days are averaged across transaction rows. Profit, margin, discount, and unit KPIs are excluded because the source does not contain the necessary fields. Customer- and time-based formulas use the PM-07 summary worksheets; refresh those summaries along with the PivotTables after replacing source data.

**Deliverable:** [Excel workbook](excel/sales_customer_analytics_calculations.xlsx) with the KPI summary and PM-07 benchmark checks.

**Status:** Completed

### PM-10 — Dashboard Development

This stage presents the validated sales and customer analysis in an interactive Excel dashboard.

**Dashboard features:** `Dashboard` is the first worksheet and includes dropdown filters for year, region, and customer segment; KPI cards for selected sales, transaction rows, sales per transaction, and average shipping days; and charts for monthly sales trend, product category mix, and sales by ship mode. All cards and chart series update when the filter selections change. Supporting chart data is kept out of view.

**Validation:** With the filters set to 2018, West, and Consumer, the dashboard returns sales of 105,851.00 across 516 transaction rows, average sales per transaction of 205.14, and average shipping duration of 3.77 days. The monthly, category, and shipping chart series each reconcile to the filtered sales total. The default All selections reconcile to total sales of 2,261,536.78 and 9,800 transaction rows.

**Deliverable:** [Excel workbook](excel/sales_customer_analytics_calculations.xlsx) with the interactive sales dashboard.

**Status:** Completed

### PM-11 — Findings and Recommendations

This stage interprets the validated analysis, distinguishes observed results from hypotheses, and summarizes practical recommendations.

**Key findings:** 2018 recorded sales grew 20.3% year over year while sales per order declined 6.2%; October–December contributed 38.5% of four-year sales; all three product categories contributed at least 31.2% of total sales; the top two states contributed 33.3%; and Consumer generated the most sales while Home Office had the highest sales per order. Profitability cannot be assessed because the source does not include cost or profit data.

**Status:** Completed

### PM-12 — Documentation

This stage finalises the project proposal and brings the key data-quality findings, analysis methods, interpretation limits, and PM-11 insights together in this README. Separate methods, data-quality, and insights reports are not maintained.

**Deliverables:** Updated [project proposal](docs/PERSONAL-PROJECT-PROPOSAL.md) and this README.

**Status:** Completed. The dataset's original source and licence could not be verified from the available project files.
