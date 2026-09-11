# R&D Cost Assessment Analytics

![Power BI](https://img.shields.io/badge/Power%20BI-Analytics-F2C811?logo=powerbi&logoColor=black)
![Data Product](https://img.shields.io/badge/Data%20Product-End--to--End-blue)
![Data Quality](https://img.shields.io/badge/Focus-Data%20Quality-green)
![Analytics](https://img.shields.io/badge/Domain-R%26D%20Tax%20Analytics-purple)

## Overview

R&D Cost Assessment Analytics is an end-to-end Business Intelligence product designed to transform fragmented R&D Tax Cost Assessment files into a **standardised, traceable and decision-ready analytical dataset**.

The project addresses both sides of the analytics lifecycle:

**Data processing and governance**

and

**Business intelligence and decision support**

The solution automates the extraction and standardisation of claim data, applies deterministic validation and versioning rules, enriches company information, and exposes the results through an interactive Power BI dashboard.

The dashboard supports analysis at three levels:

1. **Individual company**
2. **Cross-company comparison**
3. **Portfolio-wide performance**

---

## Live Project

View the project overview:

**[R&D Cost Assessment Analytics](https://rawa-elargab.github.io/cost-assessment/)**

---

# Business Problem

R&D Cost Assessment analysis was dependent on multiple Excel-based client files.

This created several challenges:

- Manual processing
- Different workbook structures
- Inconsistent naming conventions
- Multiple versions of the same claim
- Risk of duplicate counting
- Difficult company identification
- Limited portfolio-level visibility
- Limited traceability between source files and reported KPIs

The project therefore focused on a broader question:

> **How can R&D Cost Assessment data be transformed from fragmented operational files into a reliable analytical product?**

---

# Solution

The solution combines an automated data pipeline with a Power BI analytical layer.

```text
Consultant Files
      ↓
File Discovery
      ↓
Compliance Validation
      ↓
Data Extraction
      ↓
Normalisation
      ↓
Version Resolution
      ↓
Company Enrichment
      ↓
Trusted Dataset
      ↓
Power BI
      ↓
Company / Comparative / Portfolio Analytics
```

A key principle of the project is:

> **Data reliability comes before coverage.**

Files that cannot be processed deterministically are identified and logged rather than silently included using assumptions.

---

# End-to-End Data Pipeline

## 1. File Discovery

The pipeline scans the relevant source directories to identify supported Cost Assessment workbooks.

Supported MVP formats include:

```text
.xlsx
.xlsm
```

---

## 2. Compliance Validation

Before extraction, files are checked against functional rules.

Examples include:

- Valid company registration number
- Identifiable fiscal year
- Valid version information
- Expected workbook structure
- Required source tabs

Files that fail the required validation rules are classified as non-compliant.

This prevents ambiguous data from entering the analytical dataset.

---

## 3. Data Extraction

Information is extracted from defined workbook sections including:

- Control information
- Benefit information
- Cost breakdowns
- Project information
- NEST-related data

The extraction process converts workbook-based information into a structured analytical format.

---

## 4. Data Normalisation

Claims can originate from different workbook versions and structures.

Extracted information is therefore transformed into a consistent schema.

Example:

```text
Company
Company Number
Fiscal Year
Claim Version
Total Expenditure
Tax Benefit
Benefit Rate
Staffing
Subcontracting
EPWs
Software
Cloud
Data
Consumables
Other Costs
Project
Sector
Region
```

This allows claims to be compared consistently across companies and years.

---

## 5. Version Resolution

Multiple versions of the same claim may exist.

A deterministic versioning rule prevents duplicate or outdated claims from affecting the analysis.

Conceptually:

```text
Same Company
     +
Same Fiscal Year
     ↓
Identify all claim versions
     ↓
Select highest version
     ↓
If versions are equal
     ↓
Select most recent valid file
```

This ensures that only the intended claim version feeds the analytical layer.

---

## 6. Company Enrichment

Company information is enriched using official company data.

Examples include:

- Official company name
- Company registration number
- SIC classification
- Standardised sector
- Geographic information

This enriches internal claim information with consistent business dimensions for comparative and portfolio analysis.

---

# Power BI Dashboard

The Power BI product is structured around several complementary analytical views.

---

## 1. Company Analysis

<img width="926" height="1035" alt="image" src="https://github.com/user-attachments/assets/4f1fa949-2720-44bb-a194-277e6c3679f2" />


The Company page provides a detailed view of one organisation's R&D claims.

### Core KPIs

- R&D Expenditure
- Tax Benefit
- Benefit Rate
- Active Projects

### Analysis includes

- R&D expenditure trend
- Tax benefit trend
- Benefit rate trend
- Cost-category breakdown
- Year-on-year changes
- Project-level expenditure
- Portfolio weight by project

The objective is to help answer:

> **How is this company's R&D claim evolving over time, and what is driving its expenditure?**

---

# Cost Structure Analysis

The dashboard breaks R&D expenditure into standardised cost categories.

Examples include:

| Cost Category |
|---|
| Staffing |
| Subcontracting activities |
| EPWs |
| Software |
| Cloud |
| Data |
| Consumables |
| Other |

For each category, users can analyse:

- Amount
- Percentage of total expenditure
- Year-on-year movement
- Contribution to the overall cost structure

This helps identify changes in the composition of R&D investment rather than looking only at total expenditure.

---

# Project-Level Analysis

Claims can also be explored at project level.

This makes it possible to identify:

- Highest-spend projects
- Projects spanning multiple fiscal years
- Changes in project expenditure
- Cost composition by project
- Concentration of R&D investment

Multi-year projects remain associated with their corresponding fiscal-year expenditure instead of being collapsed into one combined value.

---

## 2. Comparative Analysis

<img width="1095" height="1148" alt="image" src="https://github.com/user-attachments/assets/8b999e80-2b56-441c-8a69-209970bd13a4" />


The Comparative view allows several companies to be analysed side by side.

### Comparison dimensions include

- Expenditure
- Tax Benefit
- Benefit Rate
- Cost Structure
- Fiscal Year
- Sector
- Company Scheme

### Company Snapshot

A consolidated table provides metrics such as:

```text
Company
Fiscal Year
Expenditure
Expenditure YoY
Benefit
Benefit YoY
Benefit Rate
Projects
```

This provides a quick overview before exploring detailed trends.

---

# Trend Comparison

Companies can be compared over time using:

### Expenditure Trend

Shows how qualifying R&D expenditure evolves across selected companies.

### Benefit Trend

Shows corresponding changes in R&D tax benefit.

### Cost Structure Comparison

Shows how the composition of expenditure varies between companies.

This can reveal companies with very different R&D operating models even when their total expenditure is similar.

---

## 3. Portfolio Analysis

<img width="964" height="1148" alt="image" src="https://github.com/user-attachments/assets/be272558-dab8-40ae-bf1c-b1ad98c64259" />


The Portfolio view provides a strategic overview across the full analytical population.

### Main KPIs

- Total Portfolio Expenditure
- Total Tax Benefit
- Average Benefit Rate
- Active Companies
- Number of Claims

### Analysis includes

- Expenditure trend by year
- Tax benefit trend by year
- Benefit-rate evolution
- Cost categories by fiscal year
- Company scheme distribution
- Sector analysis

The objective is to move from:

> **What happened on an individual claim?**

to:

> **What patterns are visible across the overall book of business?**

---

# Portfolio Segmentation

Portfolio-level analysis can be filtered using dimensions such as:

```text
Fiscal Year
Sector
Company Scheme
Region
Company
```

This supports analysis such as:

- Which sectors account for the most R&D expenditure?
- Which sectors generate the greatest total benefit?
- How does claim composition vary by scheme?
- How has expenditure evolved over time?
- Where are changes in benefit rates occurring?

---

## 4. Claim-Level Export

<img width="1377" height="1151" alt="image" src="https://github.com/user-attachments/assets/dac040cf-0057-47cd-8903-492a252d67db" />


The dashboard also includes an analytical export layer.

Users can filter the portfolio and access detailed claim-level records including:

- Company
- Company Number
- Fiscal Year
- Expenditure
- Benefit
- Benefit Rate
- Sector
- Region
- Scheme
- Claim Version
- Cost categories

This supports additional analysis outside the dashboard while preserving the selected analytical context.

---

# Analytical Hierarchy

The dashboard was deliberately designed around three analytical levels.

```text
                PORTFOLIO
          Strategic overview
                  ▲
                  │
             COMPARATIVE
       Cross-company analysis
                  ▲
                  │
               COMPANY
         Claim deep-dive
```

This allows different stakeholders to use the same trusted dataset for different decisions.

---

# Stakeholders

## Consultants

Primary focus:

- Individual company analysis
- Claim evolution
- Project-level expenditure
- Cost structure
- Client discussions

---

## Business Analysts / Performance Teams

Primary focus:

- Comparative analytics
- Portfolio trends
- Segmentation
- Outlier identification
- Performance monitoring

---

## Management

Primary focus:

- Total R&D expenditure
- Total benefit
- Sector trends
- Portfolio composition
- Strategic performance

---

## Data Teams

Primary focus:

- Data quality
- Pipeline monitoring
- Source traceability
- Version control
- Data lineage

---

# Key Analytical Metrics

## R&D Expenditure

Total qualifying expenditure associated with the selected claim population.

---

## Tax Benefit

Associated R&D Tax Benefit.

---

## Benefit Rate

Conceptually:

```text
Benefit Rate =
Tax Benefit
────────────
R&D Expenditure
```

This allows claims of different sizes to be compared on a relative basis.

---

## Year-on-Year Change

Year-on-year indicators highlight changes in expenditure and benefit between reporting periods.

Example:

```text
YoY Change =
(Current Year - Previous Year)
──────────────────────────────
Previous Year
```

---

# Data Quality & Governance

A significant part of the project focuses on the reliability of the analytical dataset.

## Deterministic Processing

The pipeline avoids guessing when required information cannot be resolved reliably.

---

## Version Control

Only the correct version of each claim is included in the final analytical layer.

---

## Traceability

Metrics remain traceable back through the processing pipeline to their source.

```text
Dashboard KPI
     ↓
Processed Claim
     ↓
Claim Version
     ↓
Source Workbook
```

---

## Explicit Error Handling

Non-compliant files are identified rather than silently excluded.

Typical issues can include:

- Missing identifiers
- Conflicting fiscal years
- Unsupported workbook structure
- Invalid version information
- Missing required data

This makes data-quality issues measurable and actionable.

---

# MVP Scope

## Included

- Automated extraction of compliant Excel files
- Company identification
- Claim normalisation
- Version resolution
- Company enrichment
- Cost-category analysis
- Project analysis
- Company-level analytics
- Comparative analytics
- Portfolio analytics
- Claim-level exports

## Outside Initial MVP

Examples of areas intentionally excluded from the first release include:

- Manual correction of source files
- Ambiguous records requiring judgement
- Unsupported legacy formats
- Full historical remediation
- Automatic correction of structural source issues

The design prioritises reliability before expanding coverage.

---

# Business Value

The product transforms a manual reporting process into a reusable analytical capability.

### Before

```text
Individual Excel Files
        ↓
Manual Analysis
        ↓
Inconsistent Outputs
        ↓
Limited Portfolio Visibility
```

### After

```text
Source Files
     ↓
Automated Processing
     ↓
Standardised Dataset
     ↓
Trusted Power BI Model
     ↓
Company + Comparative + Portfolio Analysis
```

The resulting product supports:

- Faster analysis
- Greater consistency
- Reduced duplication risk
- Improved traceability
- Portfolio-level visibility
- Reusable analytical outputs
- Better data-quality monitoring

---

# What This Project Demonstrates

This case study demonstrates competencies across several areas.

### Business Analysis

- Requirement definition
- KPI definition
- Business-rule translation
- Scope management
- Edge-case identification
- Stakeholder-oriented dashboard design

### Data Analytics

- Trend analysis
- Comparative analysis
- Cost composition analysis
- Portfolio segmentation
- KPI design

### Business Intelligence

- Power BI dashboard architecture
- Multi-level navigation
- Interactive filtering
- Drill-down analysis
- KPI storytelling
- Export functionality

### Data Engineering / Functional Design

- File ingestion logic
- Data validation
- Normalisation
- Deduplication
- Version control
- Enrichment
- Analytical data modelling

### Data Governance

- Data lineage
- Quality controls
- Deterministic processing
- Error handling
- Traceability
- Source-to-report consistency

### Product Thinking

- MVP definition
- User segmentation
- Analytical hierarchy
- Scalability
- Future enhancement planning
- Balance between coverage and reliability

---

# Project Architecture

```text
                SOURCE LAYER
                     │
        Excel Cost Assessment Files
                     │
                     ▼
              INGESTION LAYER
                     │
             File Discovery
                     │
                     ▼
              QUALITY LAYER
                     │
          Compliance Validation
                     │
                     ▼
            PROCESSING LAYER
                     │
       Extraction + Normalisation
                     │
                     ▼
             GOVERNANCE LAYER
                     │
       Versioning + Deduplication
                     │
                     ▼
             ENRICHMENT LAYER
                     │
          Company Information
                     │
                     ▼
              DATA MODEL
                     │
                     ▼
                 POWER BI
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       Company   Comparative  Portfolio
```


---

# Data Confidentiality

This repository demonstrates the **functional design, analytical methodology and user experience** of the solution.

The public portfolio version should contain only:

- Anonymised information
- Synthetic or demonstration data
- Aggregated metrics
- Non-sensitive business rules

No confidential source files, client information, credentials or proprietary datasets should be included.


### Areas demonstrated

- Business Intelligence
- Power BI
- Business Analysis
- Data Quality
- Data Governance
- Requirements Engineering
- Data Product Design
- Analytical Storytelling
- Data Pipeline Design
