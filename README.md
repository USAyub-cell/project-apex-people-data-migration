# Project APEX — People Data Migration Readiness Analytics Pilot

## 30-Day Senior Data Analytics Capstone Consulting Simulation

**Tools:** Excel | PostgreSQL | Power BI | Power Query | DAX  
**Domain:** People Data | Data Quality | Migration Readiness | Executive Reporting  
**Status:** Portfolio / professional capstone consulting simulation

## Executive summary

Project APEX simulates a multinational organisation preparing employee master data for migration from four operational systems: BambooHR, Active Directory, Maconomy and Xytech.

Leadership lacks a governed, repeatable view of which employee records are safe to migrate, which records require remediation and which source systems create the greatest migration risk.

The pilot creates an end-to-end analytics control framework using Excel for profiling and operational remediation, PostgreSQL for validation and transformation, and Power BI for semantic modelling and executive decision support.

## Business problem

The organisation cannot confidently authorise migration because:

- employee data is distributed across multiple source systems;
- duplicate records create migration risk;
- mandatory email data is incomplete for some employees;
- source-of-truth status is unresolved for affected records;
- validation is incomplete;
- manual quality assessment is difficult to reproduce and audit;
- executives do not have a consolidated migration-readiness view.

## Baseline findings

| Metric | Baseline |
|---|---:|
| Total employee records | 200 |
| Migration-ready records | 189 |
| Remediation-required records | 11 |
| Migration readiness | 94.5% |
| Duplicate-flagged records | 5 |
| Missing-email records | 6 |
| Source-of-truth pending | 11 |
| Validation pending | 11 |

The 11 affected records consist of five duplicate-flagged records and six missing-email records. Those same 11 records have unresolved source-of-truth and validation status.

## Proposed analytics solution

```text
Synthetic source workbook
        |
        v
Excel profiling and business validation
        |
        v
PostgreSQL
RAW -> STAGING -> DQ -> CURATED
        |
        v
Power BI semantic model
        |
        +-- Executive Migration Readiness
        +-- Data Quality
        +-- Source-of-Truth Governance
        +-- Remediation Monitoring
```

## Why each tool is used

### Excel

Excel provides the business-facing control layer for profiling, exception review, remediation tracking, reconciliation and structured handover.

### PostgreSQL

PostgreSQL provides repeatable, auditable rules for duplicate detection, missing-value identification, source-of-truth checks and creation of the migration-ready population.

### Power BI

Power BI turns the governed dataset into executive decision intelligence through a semantic model, DAX KPIs, drill-down analysis and exception reporting.

## Migration-ready rule

A record is considered migration-ready only when:

- `Duplicate_Flag = "No"`
- Email is populated
- `Missing_Email = "No"`
- `Source_of_Truth = "Confirmed"`
- `Validation_Status = "Validated"`
- `Data_Quality_Status = "Clean"`

## Repository structure

```text
01_business_case/
02_data/
03_excel/
04_sql/
05_power_bi/
06_governance/
07_qa/
08_case_study/
```

## 30-day pilot

The detailed delivery plan is in:

`01_business_case/30_DAY_PILOT_PLAN.md`

## Portfolio positioning

This repository demonstrates applied senior-level analytics capability across problem definition, data quality, SQL, Excel, semantic modelling, Power BI, KPI design, governance, QA and executive communication.

**Project APEX is a professional capstone consulting simulation using synthetic data and is not presented as paid client experience.**

## Portfolio Visual Evidence

### Executive Migration Readiness Dashboard

![Executive Migration Readiness](08_case_study/visuals/APEX_PBI_Executive_Migration_Readiness_HD.png)

Executive view of the 200-record migration baseline, showing 189 migration-ready records, 11 requiring remediation and 94.5% overall readiness.

### Data Quality & Remediation

![Data Quality and Remediation](08_case_study/visuals/APEX_PBI_Data_Quality_HD.png)

Governed exception-management view highlighting duplicate, completeness, source-of-truth and validation issues.

### Power BI Semantic Model

![Power BI Semantic Model](08_case_study/visuals/APEX_PBI_Semantic_Model_HD.png)

Fact-and-dimension analytical model supporting migration-readiness KPIs, data-quality analysis and controlled reporting.
