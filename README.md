# Industrial Analytics Pipeline (ABB-Inspired)

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-Data%20Warehouse-29B5E8?logo=snowflake&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analytics-336791?logo=postgresql&logoColor=white)
![Power%20BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Active%20Development-2EA043)

An end-to-end industrial analytics system inspired by ABB-style digital manufacturing use cases.  
This project integrates machine sensor data and plant energy data into a layered pipeline that turns raw operational records into business decisions.

---

## Overview

Industrial plants generate high-volume data across machine sensors, maintenance events, and energy systems. In practice, these streams are fragmented, messy, and often not decision-ready.

This project solves that gap with a structured analytics pipeline that:

- Integrates multiple industrial datasets
- Applies explicit data quality engineering
- Builds a medallion-style data model (RAW → CLEAN → ANALYTICS)
- Produces KPI-driven SQL outputs
- Delivers executive and operations insights in Power BI

---

## Problem Statement

Most student projects fail to show production thinking. Typical issues:

- Tool-focused storytelling instead of problem-focused storytelling
- Flat CSV analysis with no layered architecture
- No measurable quality controls
- Dashboards without business questions
- SQL with no window functions, no joins, no interpretation

This project is designed to demonstrate system thinking, business context, and engineering rigor in under 2–3 minutes of review.

---

## Why the Original Plan Fails

A weak plan usually has:

- Minimal Git history and unclear build evolution
- No architecture narrative
- SQL that answers no business decision
- Dashboard visuals that do not map to operations questions
- Interview answers that list tools but not design tradeoffs

Hiring teams can detect this quickly. The objective here is to present evidence of end-to-end ownership.

---

## The Restructured System

### Architecture Pattern

Medallion-style data flow:

RAW DATA → CLEAN LAYER → ANALYTICS LAYER → DECISION DASHBOARD

### Data Sources

- Real machine sensor dataset: AI4I 2020
- Synthetic energy dataset: machine-level and shift-level energy behavior

### Design Principles

- Separate ingestion from transformation
- Make data quality observable and auditable
- Build business-facing analytics tables, not ad hoc query outputs
- Preserve reproducibility from raw inputs to KPI outputs

---

## Key Features

### 1. Multi-Source Integration
- Joins machine telemetry and energy records using machine_id and time context
- Simulates real industrial silo integration

### 2. Data Quality Engineering
- Handles missing values, duplicates, outliers, and type mismatches
- Logs quality events and remediation actions
- Produces a quality report for traceability

### 3. Layered SQL Modeling
- RAW schema for source-faithful ingestion
- CLEAN schema for validated and standardized records
- ANALYTICS schema for KPI-ready marts

### 4. Industrial KPI Framework
- OEE (Overall Equipment Effectiveness)
- MTBF (Mean Time Between Failures)
- MTTR (Mean Time To Repair)
- Downtime Percentage
- Energy per Unit Output

### 5. Decision-Oriented BI
- Executive Summary
- Machine Health
- Energy Analytics
- Risk Alerts

Each dashboard page starts with a specific business question and ends with an actionable interpretation.

---

## KPI Definitions

- $OEE = Availability \times Performance \times Quality$
- $MTBF = \frac{\text{Operating Time}}{\text{Number of Failures}}$
- $MTTR = \frac{\text{Total Repair Time}}{\text{Number of Repairs}}$
- $Downtime\% = \frac{\text{Downtime}}{\text{Planned Production Time}} \times 100$

---

## Day-by-Day Execution (10-Day Plan)

1. Day 1: Define problem, KPIs, architecture, and project scope  
2. Day 2: Ingest AI4I machine data and profile baseline quality  
3. Day 3: Generate synthetic energy dataset with realistic operational patterns  
4. Day 4: Implement cleaning rules and quality logging framework  
5. Day 5: Validate clean outputs and produce quality report artifacts  
6. Day 6: Build RAW and CLEAN schemas in Snowflake  
7. Day 7: Build ANALYTICS tables and KPI transformations  
8. Day 8: Write business SQL queries with joins and window functions  
9. Day 9: Build 4-page Power BI dashboard connected to Snowflake  
10. Day 10: Finalize README, evidence artifacts, interview narrative, and limitations

---

## Evidence Checklist (Interview-Grade)

- [ ] 15+ meaningful commits with clean progression
- [ ] Two datasets: one real (AI4I) and one generated (energy)
- [ ] Python quality pipeline with logging and output quality report
- [ ] Snowflake schemas: RAW, CLEAN, ANALYTICS
- [ ] Minimum 5 SQL business queries
- [ ] At least one query using LAG, RANK, or PARTITION BY
- [ ] Power BI connected to Snowflake (not static CSV import)
- [ ] Four dashboard pages with clear business questions
- [ ] README includes architecture, quality, KPIs, insights, and limitations
- [ ] Interview readiness on OEE, MTBF, MTTR, and production improvements

---

## What Good vs Bad Looks Like

| Deliverable | Bad | Good |
|---|---|---|
| GitHub Repository | 3 commits, vague structure, minimal README | 18–25 meaningful commits, clean folders, architecture-to-insight README |
| SQL Queries | SELECT star style summaries, no context | Business-question headers, joins across datasets, window functions, interpretations |
| Power BI Dashboard | Random charts, no narrative | 4 focused pages, business question per page, actionable insights |
| Interview Answer | Tool list only | Decision rationale, architecture vocabulary, KPI fluency, tradeoff awareness |

---

## Business Questions This System Answers

- Which machines have the worst MTBF and require maintenance prioritization?
- Which shifts consume the most energy per unit produced?
- Is plant OEE above the operational benchmark?
- Where is downtime concentrated by machine, shift, or time window?
- Which assets show rising failure risk before severe downtime events?

---

## Interview Domination Section

Use this response style:

I designed this as a medallion architecture because industrial data is noisy and fragmented, and operations teams need auditable transformations.  
I separated RAW, CLEAN, and ANALYTICS layers to improve reliability, then modeled OEE, MTBF, MTTR, and energy efficiency so each KPI directly maps to a business decision.  
I also documented limitations and next production steps, including orchestration, automated tests, and alerting.

What to emphasize in interviews:

- Why this architecture was selected
- Why each KPI matters operationally
- How quality controls prevent bad decisions
- Which limitations remain and how to harden in production

---

## Limitations

- Batch-oriented pipeline (not real-time streaming yet)
- Synthetic energy assumptions may not fully represent all plant behaviors
- No orchestration scheduler included in current scope
- Monitoring and alerting are currently dashboard-driven, not automated

---

## Future Improvements

- Add anomaly detection for failure and energy spikes
- Add orchestrator scheduling and retry policies
- Add data tests and contract checks for schema drift
- Add near-real-time ingestion for critical assets
- Add automated alerting for KPI threshold breaches

---

## Author

Karthik Gubba  
Aspiring Data Analyst / Data Engineer  
GitHub: https://github.com/karthik-009g

---

## 2-Line Interview Pitch

I built an industrial analytics pipeline that integrates machine telemetry and energy data, enforces data quality controls, and models OEE, MTBF, MTTR, and efficiency KPIs in a layered SQL architecture.  
The result is a decision-focused Power BI system that helps teams reduce downtime, improve asset health, and optimize plant energy usage.
