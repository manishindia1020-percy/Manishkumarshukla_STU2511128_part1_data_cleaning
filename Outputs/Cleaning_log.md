# Data Cleaning Log

## Project

Retail Orders Data Cleaning and Quality Validation

---

# Objective

The objective of this project was to clean, standardize, validate, and prepare the retail orders dataset for further business analysis by improving data quality and applying business rules.

---

# Data Quality Issues Identified

The following issues were identified during the data audit process:

* Missing values in **Region**, **Ship Mode**, and **Discount** columns.
* Extra spaces and inconsistent text formatting in categorical fields.
* Mixed date formats in **Order Date** and **Ship Date** columns.
* Invalid and unrecognized date values.
* Duplicate records and duplicate Order IDs.
* Negative discount values.
* Sales and profit calculation inconsistencies.
* Invalid shipping records where the ship date occurred before the order date.
* Payment and order status records requiring business validation.

---

# Cleaning Activities Performed

## 1. Missing Value Handling

* Missing **Region** values were replaced with **"Unknown"**.
* Missing **Ship Mode** values were replaced with **"Unknown"**.
* Missing **Discount** values were replaced with **0** only when other sales-related fields were valid.

---

## 2. Text Standardization

The following fields were standardized:

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

The following Excel functions and techniques were used:

* TRIM()
* PROPER()
* SUBSTITUTE()
* Find & Replace

These steps removed unnecessary spaces, corrected inconsistent capitalization, and standardized text values.

---

## 3. Date Cleaning

Order Date and Ship Date were standardized into a consistent **YYYY-MM-DD** format.

The following validations were performed:

* Missing dates
* Invalid dates
* Mixed date formats
* Ship Date earlier than Order Date

A new field **Shipping Delay Days** was created to calculate the delivery duration.

---

## 4. Duplicate Validation

The dataset was checked for:

* Exact duplicate records
* Duplicate Order IDs containing conflicting information

Exact duplicate records were identified separately from conflicting duplicate Order IDs. Records requiring manual verification were flagged instead of being removed automatically.

---

## 5. Business Rule Validation

The following business rules were applied:

* Missing Region → Replaced with **Unknown**
* Missing Ship Mode → Replaced with **Unknown**
* Missing Discount → Replaced with **0** when applicable
* Negative Discount → Flagged as Invalid
* Invalid Shipping Records → Flagged for review
* Cancelled Orders → Excluded from completed sales calculations
* Failed Payments → Excluded from completed sales calculations
* Refunded Payments → Reported separately

---

## 6. Derived Columns Created

The following calculated fields were added:
* Order_id Flag
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
* Sales Match
* Profit Match
* Review Status
* Data Quality Flag
* Order Month
* Oredr Year

---

# Data Validation Summary

The cleaned dataset was categorized into three quality levels:

* **Clean** – Records that passed all validation checks.
* **Warning** – Records containing minor business warnings but still usable.
* **Invalid** – Records violating one or more business rules and requiring further review.

---

# Assumptions

* Missing Region and Ship Mode values were replaced with **Unknown**.
* Missing Discount values were treated as **0** only when other sales-related fields were valid.
* Original Cost values were assumed to represent total transaction cost.
* Sales and Profit calculations were performed using the cleaned fields.
* Records violating business rules were flagged instead of being deleted.

---

# Conclusion

The dataset has been successfully cleaned, validated, and standardized according to the specified project requirements. All identified data quality issues were documented, business rules were applied consistently, and the final cleaned dataset is ready for reporting, dashboard development, and further analytical tasks.