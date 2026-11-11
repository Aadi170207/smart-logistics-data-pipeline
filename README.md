# smart-logistics-data-pipeline
End-to-end Python workflow in Jupyter Notebook for data collection, integrity assessment, missing value imputation, and cleaning of smart logistics datasets

# 📦 Smart Logistics Data Collection & Cleaning Pipeline

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Cleaning-orange.svg)](https://pandas.pydata.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()

A comprehensive data engineering and analysis pipeline designed to collect, clean, and prepare public logistics and supply chain datasets for machine learning applications.

---

## 📌 Project Overview
The objective of this project is to address the data integrity challenges typical in the logistics and transportation sector. Real-world supply chain data is frequently messy, featuring missing sensor timestamps, unformatted text entries, and duplicate records. This repository implements a systematic Python-based workflow using **Pandas** and **NumPy** to transform raw data into an analysis-ready format.

---

## 📊 1. Dataset Selection & Collection Strategy
* **Source:** Kaggle (Smart Logistics & Supply Chain Dataset)
* **Rationale:** This dataset was selected because it captures multi-dimensional operational metrics—including timestamps, inventory levels, shipment statuses, environmental metrics (temperature/humidity), and transit delays—making it ideal for studying real-world data corruption and cleaning strategies.
* **Collection Strategy:** The dataset is imported locally within a Jupyter Notebook environment to allow for step-by-step inspection, data profiling, and iterative feature engineering.

---

## 🧹 2. Data Cleaning & Preprocessing Methodology
To ensure high data integrity, the pipeline addresses three primary data anomalies:

1. **Handling Missing Values:**
   * Contextual imputation: Missing values in delay reason columns are mapped to `"No Delay"` where shipments operated normally.
   * Numerical imputation: Statistical medians are applied to numeric columns to prevent distortion from extreme outliers.
2. **Duplicate Removal:**
   * Filtered and dropped fully identical row entries to prevent model bias.
3. **Format Normalization:**
   * Standardized datetime objects from raw string timestamps.
   * Trimmed trailing whitespaces from all categorical text attributes.
4. **Feature Engineering:**
   * Extracted temporal attributes (`Hour`, `DayOfWeek`, `Month`) from timestamps to support downstream machine learning models.
   * Applied one-hot encoding to categorical features (`Shipment_Status`, `Traffic_Status`).

---

## ⚙️ 3. Implementation Workflow (Jupyter Notebook)

The complete pipeline is structured across the following modular steps in the Jupyter Notebook:

* **Step 1:** Environment setup and dataset ingestion (`pd.read_csv`).
* **Step 2:** Structural profiling (`df.info()`, checking null distribution).
* **Step 3:** Data type correction and string sanitization.
* **Step 4:** Missing value management and duplicate filtering.
* **Step 5:** Temporal feature extraction and categorical encoding.
* **Step 6:** Exporting the cleaned dataset (`cleaned_smart_logistics_data.csv`).

---

## ⚠️ 4. Key Challenges in Logistics Data
* **Asynchronous Timestamps:** Inconsistent date formats across regional tracking nodes require robust parsing rules.
* **Conditional Nulls:** Missing values do not always indicate errors; often, they represent inactive states (e.g., absence of delay metrics on successful shipments).
* **High Cardinality Categories:** Handling diverse text entries for traffic conditions and transit routes requires standardized encoding strategies.

---

## 🚀 5. How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Aadi170207/smart-logistics-cleaning.git](https://github.com/Aadi170207/smart-logistics-cleaning.git)
   cd smart-logistics-cleaning
