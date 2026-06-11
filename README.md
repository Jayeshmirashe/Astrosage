# 📊 AstroSage Call Center Performance Analysis

<div align="center">

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-0078D4?style=for-the-badge&logo=databricks&logoColor=white)
![Dashboard](https://img.shields.io/badge/Dashboard-FF6F00?style=for-the-badge&logo=googleanalytics&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

<br/>

> **Analysed 28,027 consultation records across 34 days to diagnose operational gaps and deliver a data-driven ₹1 crore investment strategy for AstroSage's call center.**

</div>

---

## 📑 Table of Contents

- [Problem Statement](#-problem-statement)
- [Project Deliverables](#-project-deliverables)
- [Dataset Overview](#-dataset-overview)
- [Data Cleaning Process](#-data-cleaning-process)
- [Key Analyses & Pivot Tables](#-key-analyses--pivot-tables)
- [Dashboard Features](#-dashboard-features)
- [Key Findings & Bottlenecks](#-key-findings--bottlenecks)
- [Investment Allocation Strategy](#-investment-allocation-strategy)
- [Tech Stack & Excel Functions Used](#-tech-stack--excel-functions-used)
- [Project Structure](#-project-structure)
- [How to Navigate the Workbook](#-how-to-navigate-the-workbook)
- [Author](#-author)

---

## 🎯 Problem Statement

AstroSage, an astrology consultation platform, received a **₹1 crore investment** to optimize its call center operations. The objective was to analyse historical consultation data, identify performance gaps, and determine the most impactful way to allocate this investment across staffing, technology, training, and process improvements.

**Role:** Data Analyst — tasked with delivering end-to-end analysis from raw data to boardroom-ready recommendations.

---

## 📦 Project Deliverables

| File | Description |
|------|-------------|
| `AstroSage_Analysis_Dashboard.xlsx` | Raw data, cleaned dataset, pivot tables & interactive dashboard |
| `AstroSage_Analysis_Documentation.docx` | Detailed answers to all objective and subjective questions |
| `Astro-sage_Call_Center_Performance_Analysis.pptx` | Management presentation with insights and strategy |

---

## 🗄️ Dataset Overview

| Attribute | Detail |
|-----------|--------|
| **Total Records** | 28,027 consultation sessions |
| **Time Period** | December 2023 – January 2024 (34 days) |
| **Raw Attributes** | 35 columns |
| **Attributes After Cleaning** | 32 columns + 5 derived fields |
| **Consultation Types** | Call, Chat, Complimentary |
| **Platforms** | App, GuruCool, Dashboard |
| **Total Agents (Gurus)** | 148 |

### Core Columns

```
_id · user · chatStatus · guruName · consultationType · website
refundStatus · chatSeconds · freeCall · freeChat · createdAT
chatStartTime · chatEndTime · callChannel · callStatus · callIvrType
astrologerCallStatus · astrologerOnCallDuration · astrologersEarnings
userCallStatus · userOnCallDuration · amount · netAmount · rating · region
```

### Derived Fields Added

```
Date · Month · Year · Hour · Month_Year
```

---

## 🧹 Data Cleaning Process

Six structured steps were applied to transform the raw dataset into a reliable analytical base:

**Step 1 — Removed Duplicates**
- Checked the `_id` field for duplicate session records
- Eliminated all repeated entries before analysis

**Step 2 — Standardised Date & Time Formats**
- Converted `createdAT`, `chatStartTime`, `chatEndTime` to proper datetime format
- Extracted `Date`, `Month`, `Year`, `Hour`, `Month_Year` as new analytical columns

**Step 3 — Handled Missing & Null Values**
- Filled missing categorical values with `N/A` where appropriate
- Retained zero-duration entries for failed/incomplete sessions (they carry status meaning)

**Step 4 — Cleaned Textual Fields**
- Applied `TRIM()` and `PROPER()` to remove extra whitespace and standardise case
- Unified category labels in `consultationType` and `website` columns

**Step 5 — Converted Numeric Fields**
- Forced numeric data types on: `amount`, `netAmount`, `astrologersEarnings`, `userOnCallDuration`, `astrologerOnCallDuration`, `chatSeconds`

**Step 6 — Validated Financial Fields**
- Confirmed `netAmount` correctly reflects AstroSage's retained platform revenue
- Final cleaned dataset: **32 attributes**, ready for pivot analysis

---

## 📐 Key Analyses & Pivot Tables

### Objective Questions Answered

| # | Question | Method | Key Result |
|---|----------|--------|-----------|
| 1 | Total tables in data | Manual inspection | 1 structured table |
| 2 | Total attributes | Column count | 35 raw → 32 cleaned |
| 3 | Data cleaning | 6-step methodology | ✅ Applied |
| 4 | Daily call volume change | Pivot → Date rows, Count filter:Calls | Avg **250 calls/day** |
| 5 | Highest/lowest call months | Pivot → Month_Year rows | Dec: **8,090** · Jan: **418** |
| 6 | Total operational cost by month | Pivot → Sum of operational_cost | December highest |
| 7 | Avg calls per agent per day | Calculation | **57 calls/agent/day** |
| 8 | Repeat callers | Pivot → user frequency | Analysed & quantified |
| 9 | Revenue by consultation type | Pivot → consultationType | Calls: **79%** of total revenue |
| 10 | Calls per user/guru | Pivot → user + guru rows | Shalini: **1,060 calls** |
| 11 | Correlation: duration vs satisfaction | Scatter + analysis | Weak positive |
| 12 | Guru satisfaction scores | Pivot → guruName, avg rating | Range: 1.0 – 5.0 |
| 13 | Avg satisfaction by month | Pivot → Month_Year, avg rating | Overall avg: **2.93** |
| 14 | Categorical column count | Column type inspection | Identified |

---

## 📊 Dashboard Features

The interactive dashboard was built for senior management with the following components:

### KPI Cards (Snapshot Metrics)

| Metric | Value |
|--------|-------|
| 💰 Total Revenue | ₹2,13,987.32 |
| 📅 Total Days | 34 |
| 📞 Total Calls | 8,508 |
| 💬 Total Chats | 19,514 |
| 👤 Total Gurus | 148 |
| ⭐ Average Rating | 2.93 / 10 |
| 📊 Avg Calls per Agent | 57 |

### Charts & Visualisations

- 📈 **Hourly Call Distribution** — identifies peak demand windows
- 📅 **Day-wise Call Volume Trend** — daily fluctuation pattern
- 🍩 **Revenue by Consultation Type** — Call vs Chat vs Complimentary split
- 🌐 **Website-wise Distribution** — App vs GuruCool vs Dashboard
- 📊 **Chat Status Distribution** — Completed / Incomplete / Failed breakdown
- ⭐ **User Rating Distribution** — satisfaction frequency chart
- 🏆 **Top 10 Gurus by Calls Handled** — agent workload view
- 📉 **Rating-wise Guru Distribution** — performance spread

### Interactive Slicers

```
[ Consultation Type ]   [ Year ]   [ Website ]
```

Slicers allow management to dynamically filter the entire dashboard across time periods, platforms, and service types — enabling live exploration during boardroom discussions.

---

## 🔍 Key Findings & Bottlenecks

### 1. 🚨 Severe Workload Imbalance
- **Astro Shalini handled 1,060 calls** — the highest single-agent load
- The average across 128 call-handling gurus was just **66 calls**
- A small group of top gurus consistently exceeded this benchmark by 15x+
- **Impact:** Burnout risk for high-load gurus, wasted capacity from underutilised ones

### 2. 📅 Extreme Monthly Demand Swings
- **December peak: 8,090 calls** — the highest volume month
- **January trough: 418 calls** — the lowest volume month
- A **19× swing** between peak and trough with no adaptive staffing in place

### 3. ⏰ Concentrated Peak-Hour Pressure
| Hour | Calls |
|------|-------|
| 8 AM | 660 |
| 10 AM | 605 |
| 7 AM | 551 |
| 11 AM | 515 |

- Demand concentrated between **6 AM and 5 PM**
- Same overloaded gurus absorb this peak pressure daily

### 4. ⭐ Low Customer Satisfaction (2.93 / 10)
- **Rating of 0** was the single most-recorded score — indicating many sessions end without any rating (failed/incomplete)
- **Complimentary consultations** had the highest rating: **4.5**
- **Chat consultations** had the lowest: **2.69**
- **Call consultations** sat at **3.50** — better but still below acceptable

### 5. 🌐 Platform Performance Gap
| Platform | Avg Rating | User Volume |
|----------|-----------|-------------|
| App | 3.5 | — |
| GuruCool | 2.72 | 20,225 users |
| Dashboard | — | — |

- GuruCool handles the **most users** yet has the **lowest satisfaction score** — a critical UX problem

### 6. 💸 Revenue Concentration Risk
- **Calls generate 79% of total revenue** vs chat contributing a minority share
- Any disruption to call infrastructure has outsized financial impact
- Heavy reliance on a single revenue stream creates operational fragility

---

## 💡 Investment Allocation Strategy

Based on the analysis, the ₹1 crore investment was allocated across 5 priority areas:

```
┌─────────────────────────────────────────────────────────────────┐
│                 ₹1 CRORE INVESTMENT ROADMAP                     │
├──────────────────────────────────┬──────────────┬──────────────┤
│ Area                             │ Allocation   │ Amount       │
├──────────────────────────────────┼──────────────┼──────────────┤
│ 🖥️  Technology & Infrastructure  │     30%      │ ₹30,00,000   │
│ 👥  Workforce Expansion          │     25%      │ ₹25,00,000   │
│ 🎓  Training & Quality           │     20%      │ ₹20,00,000   │
│ 💛  Customer Experience          │     15%      │ ₹15,00,000   │
│ 📣  Revenue & Marketing          │     10%      │ ₹10,00,000   │
└──────────────────────────────────┴──────────────┴──────────────┘
```

**Why this split:**
- **Technology (30%)** — Highest priority because failed/busy/no-answer calls are destroying revenue and satisfaction simultaneously
- **Workforce (25%)** — Workload imbalance (66 avg vs 1,060 peak) is the clearest operational bottleneck in the data
- **Training (20%)** — Overall rating of 2.93 signals skill gaps; chat consultations at 2.69 need immediate attention
- **Customer Experience (15%)** — GuruCool's 2.72 rating despite highest volume shows UX friction is measurable and fixable
- **Marketing (10%)** — Category-wise revenue analysis shows profitable services are under-promoted

---

## 🛠️ Tech Stack & Excel Functions Used

### Excel Features
| Category | Features Used |
|----------|--------------|
| **Data Cleaning** | `TRIM()`, `PROPER()`, `COALESCE`, Remove Duplicates, Find & Replace |
| **Date/Time** | `TEXT()`, `YEAR()`, `MONTH()`, `DAY()`, `HOUR()`, Custom date parsing |
| **Aggregation** | `SUM()`, `AVERAGE()`, `COUNT()`, `COUNTIF()`, `COUNTA()` |
| **Lookup** | `VLOOKUP()`, `INDEX-MATCH` |
| **Pivot Tables** | Row/Column grouping, Value field settings, % of total, Filters |
| **Visualisation** | Bar charts, Line charts, Donut/Pie charts, Clustered column charts |
| **Dashboard** | Slicers, Timeline filters, Conditional formatting, KPI cards |

### Workbook Sheets

```
📋 RAW_DATASET         — Original 28,027 records as imported
🧹 CLEANED_DATASET     — Preprocessed data ready for analysis
📐 OBJECTIVE_PIVOTS    — All 14 objective question pivot tables
💡 SUBJECTIVE_PIVOTS   — Subjective analysis pivot tables
📊 DASHBOARD           — Interactive KPI dashboard with slicers
```

---

## 📁 Project Structure

```
astrosage-call-center-analysis/
│
├── 📊 AstroSage_Analysis_Dashboard.xlsx       ← Main workbook (5 sheets)
│   ├── RAW_DATASET
│   ├── CLEANED_DATASET
│   ├── OBJECTIVE_PIVOTS
│   ├── SUBJECTIVE_PIVOTS
│   └── DASHBOARD
│
├── 📄 AstroSage_Analysis_Documentation.docx   ← Full Q&A documentation
│
├── 📽️ Astro-sage_Call_Center_Performance_Analysis.pptx  ← Management deck
│
└── 📖 README.md                               ← This file
```

---

## 🧭 How to Navigate the Workbook

1. **Start with `DASHBOARD`** — get an instant overview using the KPI cards and slicers
2. **Use the slicers** (Consultation Type / Year / Website) to filter all visuals simultaneously
3. **Visit `OBJECTIVE_PIVOTS`** for granular breakdowns behind each KPI
4. **Visit `SUBJECTIVE_PIVOTS`** for agent workload, satisfaction, and platform analysis
5. **Reference `CLEANED_DATASET`** if you want to verify any number from source
6. **Read `Documentation.docx`** for the full analytical narrative and investment recommendations

> ⚠️ **Note:** Enable macros and content when opening the file if prompted — slicers require active connections to pivot tables.

---

## 👤 Author

**Jayesh Mirashe**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username)

---

<div align="center">

*If this project helped you, consider giving it a ⭐ on GitHub!*

</div>
