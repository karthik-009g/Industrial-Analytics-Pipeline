# Industrial Analytics Pipeline

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python\&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas\&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-Data%20Warehouse-29B5E8?logo=snowflake\&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analytics-336791?logo=postgresql\&logoColor=white)
![Power%20BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi\&logoColor=black)
![Status](https://img.shields.io/badge/Status-Active%20Development-2EA043)

An end-to-end industrial analytics system for manufacturing-style use cases.
This project integrates machine sensor data and plant energy data into a layered pipeline that turns raw operational records into business insights.

---

## Overview

Industrial plants generate high-volume data across machine sensors, maintenance events, and energy systems. In practice, these streams are fragmented, messy, and often not decision-ready.

This project builds a structured analytics pipeline that:

* Integrates multiple industrial datasets
* Applies explicit data quality engineering
* Builds a medallion-style data model (RAW → CLEAN → ANALYTICS) 
* Produces KPI-driven SQL outputs
* Delivers insights in Power BI

---

## Problem Statement

Industrial environments commonly face:

* Fragmented data across systems
* Inconsistent or incomplete sensor readings
* Analysis on raw, unvalidated data
* Lack of direct linkage between data and decisions

This project addresses these challenges by building a layered analytics system with clear data quality controls and business-focused outputs.

---

## System Architecture

Medallion-style data flow:

RAW DATA → CLEAN LAYER → ANALYTICS LAYER → DASHBOARD

### Data Sources

* Machine sensor dataset: AI4I 2020
* Synthetic energy dataset: machine-level and shift-level energy behavior

### Design Principles

* Separate ingestion from transformation
* Make data quality observable and traceable
* Build business-facing analytics tables
* Preserve reproducibility from raw inputs to KPI outputs

---

## Key Features

### 1. Multi-Source Integration

* Joins machine telemetry and energy records using `machine_id`
* Simulates integration across operational data sources

### 2. Data Quality Engineering

* Handles missing values, duplicates, outliers, and type mismatches
* Logs quality events and remediation actions

### 3. Layered SQL Modeling

* RAW schema for source-faithful ingestion
* CLEAN schema for validated records
* ANALYTICS schema for KPI-ready tables

### 4. Industrial KPI Framework

* OEE (Overall Equipment Effectiveness)
* MTBF (Mean Time Between Failures)
* MTTR (Mean Time To Repair)
* Downtime Percentage
* Energy per Unit Output

### 5. Decision-Oriented BI

* Executive Summary
* Machine Health
* Energy Analytics
* Risk Indicators

---

## KPI Definitions

* OEE = Availability × Performance × Quality
* MTBF = Operating Time / Number of Failures
* MTTR = Total Repair Time / Number of Repairs
* Downtime% = (Downtime / Planned Production Time) × 100

---

## Project Workflow (10-Day Plan)

1. Define problem, KPIs, and architecture
2. Ingest machine sensor dataset
3. Generate synthetic energy dataset
4. Inject data quality issues
5. Apply cleaning and validation logic
6. Build RAW and CLEAN layers
7. Create ANALYTICS tables
8. Write business SQL queries
9. Build Power BI dashboard
10. Finalize documentation and outputs

---

## Business Questions Answered

* Which machines have the lowest MTBF?
* Which shifts consume the most energy per unit?
* Where is downtime concentrated?
* Are efficiency metrics within expected thresholds?

---

## Project Structure

industrial-analytics-pipeline/
│
├── data/
│   ├── raw_data/
│   └── cleaned_data/
│
├── src/
│
├── sql/
│
├── powerbi/
│
├── docs/
│
└── README.md

---

## Limitations

* Batch-oriented pipeline (no real-time processing)
* Synthetic energy data simplifies real-world variability
* No orchestration layer included

---

## Future Improvements

* Add anomaly detection models
* Implement orchestration and scheduling
* Add automated data validation tests
* Extend to near real-time ingestion

---

## Author

Karthik Gubba
GitHub: https://github.com/karthik-009g

---

## Summary

This project demonstrates how raw industrial data can be transformed into structured, reliable insights using a layered pipeline combining data engineering, SQL modeling, and business-oriented analytics.
