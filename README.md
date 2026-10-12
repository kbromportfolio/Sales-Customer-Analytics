# Sales & Customer Analytics

**Project Status:** In Progress

**Primary Tool:** Microsoft Excel

**Supporting Tools:** Git & GitHub

**Dataset:** Retail sales and customer transaction dataset

**Analysis Type:** Sales performance, customer segmentation, product analytics, and regional trend analysis

This project evaluates sales performance and customer behaviour using a retail transaction dataset. The objective is to clean and validate the source data, structure Excel-based analysis, and produce a clear overview of revenue drivers, customer patterns, and business trends that can be communicated through summary reporting and dashboard visuals.

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
* Data quality checks are performed before analysis begins.
* Results should be interpreted within the context of the available dataset and business assumptions.

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
│   ├── PERSONAL PROJECT PROPOSAL.odt
│   ├── PERSONAL-PROJECT-PROPOSAL.md
│   ├── PROJECT MANAGEMENT TRACKER.odt
│   └── ~$OJECT MANAGEMENT TRACKER.odt
│
├── reports/
│   └── (analysis outputs to be created)
│
├── Images/
│   └── (visual outputs to be created)
│
├── excel/
│   └── (Excel workbook files to be created)
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

This stage confirms the dataset source, reviews its fields and date formats, checks the applicable licence or usage conditions, and preserves the original raw data without modification.

**Deliverable:** Source record and preserved [raw dataset](Data/Raw/train.csv).

**Status:** Completed

### PM-03 — Data Profiling

This stage inspects the dataset's columns, data types, missing values, duplicates, value ranges, and key identifiers to identify quality issues that may affect the analysis.

**Deliverable:** Data profiling report.

**Status:** Completed

### PM-04 — Data Cleaning

This stage applies the verified date-format correction to the two date columns, converting them to ISO `YYYY-MM-DD` format. No exact duplicate rows were found, and no records were removed. The 11 missing `Postal Code` values are retained because their values cannot be confirmed from the source data.

**Deliverable:** [Cleaned dataset](Data/Cleaned/train_cleaned.csv).

**Status:** Completed

### PM-05 — Data Validation

This stage verifies date formats and order, required identifiers, sales values, and record counts in the cleaned dataset against the preserved raw source.

**Validation notes:**

* 9,800 records and 18 fields match the raw source.
* All cleaned date values parse successfully as ISO `YYYY-MM-DD`, and no ship date precedes the order date.
* All `Row ID`, `Order ID`, `Customer ID`, and `Product ID` values are populated, and all `Row ID` values are unique.
* All sales values are numeric and non-negative, ranging from 0.444 to 22,638.48.
* The 11 missing `Postal Code` values remain blank because they were not confirmed in the source data.

**Status:** Completed
