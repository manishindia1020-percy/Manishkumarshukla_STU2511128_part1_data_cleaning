# Retail Orders Data Cleaning & Quality Assessment

## Project Overview

This project focuses on improving the quality, consistency, and reliability of a retail orders dataset by performing comprehensive data cleaning, validation, and business rule implementation using Microsoft Excel. The objective was to transform raw, inconsistent data into a structured and analysis-ready dataset that supports accurate business reporting and decision-making.

The project involved identifying and resolving missing values, inconsistent text entries, mixed date formats, duplicate records, invalid discounts, shipping anomalies, and calculation inconsistencies. A complete data quality assessment report and multiple analytical pivot summaries were also developed to evaluate the overall condition of the dataset.

---

# Project Objectives

* Perform a comprehensive data quality assessment.
* Handle missing values using predefined business rules.
* Standardize categorical text fields.
* Clean and validate date fields.
* Detect duplicate records and conflicting Order IDs.
* Apply business validation rules.
* Create calculated business metrics.
* Generate data quality reports.
* Build analytical Pivot Tables for business insights.
* Prepare an analysis-ready dataset.

---

# Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Functions

  * IF
  * IFERROR
  * COUNTIF
  * COUNTIFS
  * SUMIF
  * TEXT
  * DATE
  * YEAR
  * MONTH
  * TRIM
  * PROPER
  * SUBSTITUTE
  * ABS
  * ISNUMBER
* Sorting & Filtering
* Conditional Formatting

---

# Data Cleaning Process

## 1. Missing Value Handling

The dataset was examined for missing values in critical business fields.

Actions performed:

* Missing **Region** values were replaced with **"Unknown"**.
* Missing **Ship Mode** values were replaced with **"Unknown"**.
* Missing **Discount** values were replaced with **0** only when all related sales fields were valid.

---

## 2. Text Standardization

The following fields were cleaned and standardized:

* Customer Name
* Segment
* Region
* State
* City
* Category
* Sub Category
* Ship Mode
* Payment Status
* Order Status

Cleaning activities included:

* Removing leading and trailing spaces
* Removing unnecessary spaces
* Standardizing capitalization
* Correcting inconsistent category names
* Removing unwanted characters where applicable

---

## 3. Date Cleaning & Validation

Order Date and Ship Date contained multiple date formats and inconsistent values.

The following validations were performed:

* Missing dates
* Invalid dates
* Mixed date formats
* Ship Date earlier than Order Date

Both date fields were standardized into a consistent **YYYY-MM-DD** format.

Additional derived fields created:

* Shipping Delay Days
* Order Month
* Order Year

---

## 4. Duplicate Detection

The dataset was analyzed for duplicate records.

Validation included:

* Exact duplicate rows
* Duplicate Order IDs with conflicting information

Instead of removing conflicting records automatically, they were flagged for manual review to preserve data integrity.

---

## 5. Business Rule Implementation

The following business rules were applied throughout the cleaning process:

| Business Rule            | Action Taken                               |
| ------------------------ | ------------------------------------------ |
| Missing Region           | Replaced with "Unknown"                    |
| Missing Ship Mode        | Replaced with "Unknown"                    |
| Missing Discount         | Replaced with 0 where applicable           |
| Negative Discount        | Flagged as Invalid                         |
| Invalid Shipping Records | Flagged for review                         |
| Cancelled Orders         | Excluded from completed sales calculations |
| Failed Payments          | Excluded from completed sales calculations |
| Refunded Payments        | Reported separately                        |

---

# Calculated Columns Created

The following derived fields were generated to support analysis:

* Clean Order Date
* Clean Ship Date
* Shipping Delay Days
* Order Month
* Order Year
* Discount Flag
* Payment Status Flag
* Order Status Flag
* Calculated Sales
* Calculated Profit
* Calculated Profit Margin
* Sales Match Indicator
* Profit Match Indicator
* Review Status
* Data Quality Flag

---

# Data Quality Report

A comprehensive data quality report was created containing:

* Missing Value Summary
* Duplicate Summary
* Invalid Discount Summary
* Date Validation Summary
* Order & Payment Status Summary
* Sales & Profit Calculation Mismatch Summary
* Final Clean vs Flagged Record Summary

These reports provide a complete overview of the quality improvements applied to the dataset.

---

# Pivot Summary Report

Analytical Pivot Tables were created to summarize key business metrics.

The report includes:

* Sales & Profit by Region
* Sales & Profit by Category and Sub Category
* Order Count by Ship Mode
* Profit Margin by Customer Segment
* Refunded / Cancelled / Failed Orders by Region
* Monthly Sales Trend

Sorting and filtering were applied to selected Pivot Tables as required.

---

# Final Data Quality Summary

| Category                | Status |
| ----------------------- | ------ |
| Total Records Processed | 932    |
| Clean Records           | 563    |
| Warning Records         | 143    |
| Invalid Records         | 226    |

The final dataset was categorized based on business validation rules to clearly distinguish records ready for analysis from those requiring additional review.

---

# Key Outcomes

* Improved overall data consistency and quality.
* Standardized all major categorical fields.
* Converted inconsistent date formats into a single standard format.
* Implemented business validation rules for reliable reporting.
* Identified duplicate and conflicting records.
* Generated business-ready calculated metrics.
* Produced structured quality reports and analytical summaries.
* Delivered a clean dataset suitable for reporting, dashboard creation, and advanced analytics.

---

# Project Folder Structure

```
Part1-Data_Cleaning/
│
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
│
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
│
├── screenshots/
│
└── README.md
```

---

# Assumptions

* Missing Region and Ship Mode values were replaced with **"Unknown"**.
* Missing Discount values were treated as **0** only when related sales information was valid.
* Original Cost values were assumed to represent transaction-level cost.
* Business rule violations were flagged rather than deleted.
* Conflicting duplicate Order IDs were retained for review instead of being removed automatically.

---

# Conclusion

This project demonstrates a complete end-to-end data cleaning workflow using Microsoft Excel. The dataset was successfully standardized, validated, and enriched with calculated business metrics while maintaining transparency through detailed quality reports and documentation. The final cleaned dataset is reliable, analysis-ready, and suitable for business reporting, dashboard development, and further analytical applications.
