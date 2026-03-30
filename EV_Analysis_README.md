# Electric Vehicle Production Lifecycle & Market Dynamics Analysis (2010–2024) ⚡

> **Self-Initiated Project** &nbsp;|&nbsp; Alteryx Designer &nbsp;|&nbsp; Time-Series & Lifecycle Analysis &nbsp;|&nbsp; Data Preparation & Visualization

---

## Project Overview

The EV industry between 2010 and 2024 is not a simple growth story — it is a story of volatility, strategic pauses, innovation surges, and market consolidation. This project analyzes **14 years of EV production data** entirely within **Alteryx Designer** to surface the patterns that explain how the EV market actually evolved.

The analysis is structured as a **two-module end-to-end pipeline** — from raw data preparation through to lifecycle insights — simulating how production analytics are generated in real-world business environments.

> **Dataset coverage:** 2010–2024 only. Year 2025 excluded due to incomplete records.
> **Fields used:** Model Year · Make (Manufacturer) · Model (EV model name)

---

## Business Objectives

| # | Objective |
|---|---|
| 1 | Identify the years with the **largest production increases and decreases** |
| 2 | Detect EV models that experienced **long production pauses** then made confirmed comebacks |
| 3 | Find the years with the **highest number of newly introduced EV models** (innovation cycles) |
| 4 | Identify **model extinction events** — models that stopped production year-over-year |
| 5 | Demonstrate time-series logic, lifecycle analysis, and Alteryx pipeline design end-to-end |

---

## Tools & Alteryx Components Used

| Tool | Purpose |
|---|---|
| **Filter** | Exclude 2025 partial records, isolate relevant year ranges |
| **Sort** | Order records by Make, Model, and Year for sequential logic |
| **Summarize** | Aggregate total production counts by year, manufacturer, model |
| **Multi-Row Formula** | Year-over-year calculations and gap detection across sequential rows |
| **Formula** | Derive flags for new models, extinct models, comeback detection |
| **Sample** | Extract top-ranked results (top 3 comeback models, peak innovation year) |
| **Union** | Combine datasets for cross-module analysis |
| **Select** | Manage and clean field selection at each pipeline stage |
| **Interactive Chart** | Visualize production trends, innovation surges, and lifecycle events |
| **Render** | Export final visual reports |

> No hardcoded year logic was used — all workflows dynamically adapt to the dataset.

---

## Workflow Structure

### Module 1 — `EV Data Preparation Project.yxzp`
**Production Trends & Model Comeback Analysis**

```
[Raw EV Data Input]
        │
        ▼
[Filter]               → Exclude 2025 partial records
        │
        ▼
[Sort]                 → Order by Make → Model → Year
        │
        ▼
[Summarize]            → Total production count per year
        │
        ▼
[Multi-Row Formula]    → Calculate YoY production change
        │
        ▼
[Formula]              → Flag production gaps per model
        │
        ▼
[Sample]               → Extract top 3 longest comeback models
        │
        ▼
[Output]               → Production trend table + comeback rankings
```

### Module 2 — `EV Data Preparation Project Part 2.yxzp`
**Innovation & Model Extinction Analysis**

```
[Prepared Data from Module 1]
        │
        ▼
[Formula]              → Flag first-appearance year per model (new models)
        │
        ▼
[Summarize]            → Count new models introduced per year
        │
        ▼
[Multi-Row Formula]    → Year-over-year model existence comparison
        │
        ▼
[Formula]              → Flag extinction events (model in year Y, absent in Y+1)
        │
        ▼
[Summarize]            → Count extinction events per year
        │
        ▼
[Interactive Chart]    → Visualize innovation surges + extinction periods
        │
        ▼
[Render]               → Export final lifecycle report
```

---

## Key Insights & Interview Talking Points

### 1. EV Production is Not Linear — It is Volatile

EV production growth between 2010 and 2024 was not steady. There were specific years where production surged sharply, and other years where it dropped noticeably. This volatility reflects external pressures — policy shifts, supply chain disruptions, and competitive dynamics — rather than smooth organic growth.

**What this means for a business:** Production planning and demand forecasting for EV manufacturers cannot rely on simple trend extrapolation. Year-specific volatility must be accounted for in any supply chain or inventory model.

---

### 2. Some EV Models Disappeared — Then Came Back

The analysis identified EV models that went through **confirmed production pauses** (gaps of multiple years) before returning to market. These are not failed models — they represent **strategic repositioning**: manufacturers pulling a model to retool, reposition, or wait for market conditions to improve, then re-entering.

**Top 3 models with the longest confirmed production pauses and comebacks** were ranked using gap detection logic built with Multi-Row Formula in Alteryx.

**What this means for a business:** Model lifecycle management is not just about launch and discontinuation — it includes revival strategies. Understanding which models historically came back can inform competitive intelligence and product roadmap decisions.

---

### 3. Innovation Does Not Spread Evenly — It Clusters in Specific Years

New model introductions (first-appearance detection) were not evenly distributed across 2010–2024. Instead, they **clustered in specific years**, driven by a small number of manufacturers introducing multiple models at once — often coinciding with regulatory changes or technology breakthroughs.

**What this means for a business:** Innovation surges signal inflection points in the market. A sudden rise in new model introductions is a leading indicator of increased competition ahead — useful for competitive monitoring teams.

---

### 4. High Innovation Periods Were Followed by High Extinction Periods

One of the most important patterns the analysis revealed: **years with the highest number of new model introductions were often followed by years with the highest number of model extinctions.** Not every model that entered the market survived.

This reflects classic market consolidation behavior — many entrants, then a shake-out — which mirrors what happened in the broader EV market as established manufacturers outcompeted smaller players.

**What this means for a business:** Tracking both innovation entry rates and extinction rates together gives a more accurate picture of market health than tracking either alone.

---

### 5. Manufacturer-Level Innovation Was Concentrated

The breakdown of new model introductions by manufacturer showed that innovation was **concentrated among a few key players** rather than distributed evenly. A small number of manufacturers accounted for the majority of new model introductions in peak years.

**What this means for a business:** Market share in innovation is as important as market share in production volume. A manufacturer leading in new model introductions one year is likely to lead in production volume 2–3 years later.

---

## Key Techniques Applied

| Technique | How it was built in Alteryx |
|---|---|
| Year-over-year production change | Multi-Row Formula comparing current vs previous year total |
| Production gap detection | Multi-Row Formula tracking consecutive year gaps per model group |
| New model first-appearance detection | Formula flagging where a Make+Model combination appears for the first time |
| Extinction event detection | Multi-Row Formula checking if a model present in year Y is absent in year Y+1 |
| Top-N ranking | Sample tool applied after sorting by gap length / count |
| Dynamic year logic | No hardcoded years — all filters and ranges derived from the data itself |

---

## Workflow Screenshots

| Screenshot | What it shows |
|---|---|
| `Screenshot 2026-02-06 233212.png` | Module 1 — full workflow canvas |
| `Screenshot 2026-02-06 233305.png` | Input data structure and field overview |
| `Screenshot 2026-02-06 233445.png` | Filter and sort logic applied |
| `Screenshot 2026-02-06 233513.png` | Multi-Row Formula — YoY production change |
| `Screenshot 2026-02-06 233546.png` | Production gap detection output |
| `Screenshot 2026-02-06 233622.png` | Module 2 — full workflow canvas |
| `Screenshot 2026-02-06 233649.png` | New model first-appearance detection |
| `Screenshot 2026-02-07 235235.png` | Innovation surge + extinction chart |
| `Screenshot 2026-02-07 235313.png` | Final rendered lifecycle report output |

---

## Repository Structure

```
EV-Production-Lifecycle-Analysis/
│
├── EV Data Preparation Project.yxzp         ← Module 1: Production trends & comebacks
├── EV Data Preparation Project Part 2.yxzp  ← Module 2: Innovation & extinction analysis
├── README.md                                ← This file
│
└── Screenshots/                             ← Workflow and result captures (Feb 2026)
    ├── Screenshot 2026-02-06 233212.png
    ├── Screenshot 2026-02-06 233305.png
    ├── Screenshot 2026-02-06 233445.png
    ├── Screenshot 2026-02-06 233513.png
    ├── Screenshot 2026-02-06 233546.png
    ├── Screenshot 2026-02-06 233622.png
    ├── Screenshot 2026-02-06 233649.png
    ├── Screenshot 2026-02-07 235235.png
    └── Screenshot 2026-02-07 235313.png
```

---

## How to Run

1. Download both `.yxzp` files from this repository
2. Open **Alteryx Designer** (2022.1 or later recommended)
3. Open `EV Data Preparation Project.yxzp` → connect your EV dataset → Run
4. Open `EV Data Preparation Project Part 2.yxzp` → connect output from Module 1 → Run
5. Charts render in Interactive Chart tools — use Render tool to export as PDF

---

## Skills Demonstrated

| Skill | Evidence |
|---|---|
| Data preparation & cleansing | Null removal, year filtering, field standardization |
| Time-series logic | YoY calculations using Multi-Row Formula |
| Lifecycle analysis | Gap detection, first-appearance flagging, extinction detection |
| Alteryx pipeline design | Two-module modular workflow — preparation separated from analysis |
| Business insight generation | 5 distinct business-relevant findings from raw production data |
| Dynamic workflow design | No hardcoded values — all logic adapts to dataset |

---

## About the Author

**Adhitya Yellapu** — B.Tech Graduate, Electrical & Electronics Engineering
Acharya Nagarjuna University, Guntur &nbsp;|&nbsp; CGPA: 7.89

- 🏅 Alteryx Designer **Core Certified** | Pursuing **Advanced**
- 💼 [LinkedIn](https://linkedin.com/in/adhitya-yellapu)
- 📧 y21ee3260@gmail.com
- 🗂️ [GitHub Profile](https://github.com/ADHITYAYELLAPU)

---

> *Self-initiated project. Built to demonstrate end-to-end data preparation, time-series logic, and lifecycle analysis skills using Alteryx Designer on 14 years of real-world EV production data.*
