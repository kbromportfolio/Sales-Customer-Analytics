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

* Retail sales transaction records
* Customer, product, and geographic fields included
* Order and ship dates available for time-based analysis
* Sales values included for revenue analysis
* Suitable for segment, category, geography, and product review

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
│       └── cleaned_dataset.csv
│
├── docs/
│   ├── PERSONAL-PROJECT-PROPOSAL.md
│   └── PROJECT MANAGEMENT TRACKER.odt
│
├── reports/
│   └── analysis_outputs/
│
├── Images/
│   └── dashboard_visuals/
│
├── excel/
│   └── analysis_workbook.xlsx
│
├── README.md
├── .gitignore
└── LICENSE
```

## Project Methodology

The project follows a structured workflow from planning through final review and documentation.

### PM-01 — Project Planning

This stage establishes the project purpose, goals, and scope. The focus is to define the business problem, identify the analytical questions to answer, and map out the project workflow before any data work begins.

The project plan includes the overall aim, key objectives, dataset context, methodological approach, and the expected outputs. The work is structured to ensure that each analysis stage builds logically on the previous one and that the final deliverable remains aligned with the project purpose.

### PM-02 — Dataset Preparation

This stage focuses on confirming the source data, reviewing the available fields, checking date formatting, and confirming the licensing or usage conditions associated with the dataset. The purpose is to ensure that the project starts from a reliable and properly understood source before any transformation or analysis is performed.

The raw dataset is preserved without modification so that a traceable original record remains available throughout the project. This allows for validation, auditability, and comparison against any cleaned or transformed files created later in the workflow.



