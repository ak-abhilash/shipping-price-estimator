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

## How to Run

> Works on Databricks CE (Community Edition)

