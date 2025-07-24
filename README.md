# Shipping Price Estimator – Databricks (PySpark)

A mini-project to estimate shipping costs for e-commerce orders based on product weight, delivery distance, and pricing thresholds — with free shipping logic for high-value items.

> Built with Databricks Community Edition + PySpark using synthetic data

---

## Problem Statement

Modern e-commerce platforms need to dynamically calculate shipping costs that are fair, scalable, and margin-aware. This project simulates a basic shipping cost estimation logic based on:

- Product weight
- Distance between supplier and customer
- Pricing sensitivity (free shipping for high-margin items)

---

## Tech Stack

- **Databricks Community Edition**
- **PySpark**

---

## Dataset

A synthetic version of an Amazon-like sales dataset was used (`Amazon_Sale_Report.csv`), including columns like:

- `SKU`, `Qty`, `Amount`, `ship-city`

Additional columns like **product dimensions**, **supplier city**, and **distance** are generated programmatically using UDFs.

---

## Pipeline Steps

1. **Read CSV**  
2. **Clean data** — remove nulls  
3. **Add product dimensions** — weight, size  
4. **Assign supplier cities** — randomly  
5. **Estimate distance** — mock logic  
6. **Calculate shipping cost** — `weight * distance * rate`  
7. **Apply free shipping logic** — if unit price > ₹500  
8. **Write to Parquet** — `/FileStore/output/shipping_estimation_results`

---

## Setup Instructions

1. Sign up at [Databricks Community Edition](https://community.cloud.databricks.com/)  
2. Create a new notebook and upload the `Amazon_Sale_Report.csv`  
3. Attach the notebook to a cluster (you can use default config)  
4. Ensure the CSV and notebook are in the same workspace folder

---

## How to Run

1. Open the uploaded notebook in Databricks  
2. Run each cell sequentially  
3. Output will be written to:  
   `/FileStore/output/shipping_estimation_results`  
4. Use `%fs ls /FileStore/output/` to inspect or download the output

---

## Output

The final output is written as a Parquet file and contains enriched shipping data per order line, including estimated cost and free shipping status.

---

## Notes

- Distances and weights are randomly generated using mock logic  
- You can replace city distances with real data or use external APIs  
- Extendable to support other business rules and pricing strategies  
