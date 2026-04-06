# ⚡ Electric Vehicle Production Lifecycle & Market Dynamics Analysis (2010–2024)
### Enterprise-Grade Time-Series & Lifecycle Analytics | Alteryx Designer · Multi-Row Formula · YoY Volatility · Innovation Tracking

> **15 years. 50+ EV models. Multiple global manufacturers.** — A structured analytical study of how the EV industry grew, stalled, reinvented, and consolidated — built entirely in Alteryx Designer with zero hardcoded logic.

---

## 📌 Project at a Glance

| Dimension | Scope |
|---|---|
| 📅 Time Span Analyzed | **15 years — 2010 to 2024** |
| 🚗 Unique EV Models Tracked | **50+ models** across multiple manufacturers |
| 🏭 Analysis Type | **Year-over-Year Volatility · Lifecycle Gap Detection · Innovation Tracking · Extinction Analysis** |
| 🔧 Tool | **Alteryx Designer** — Filter · Sort · Summarize · Multi-Row Formula · Formula · Sample · Union · Select |
| 📐 Workflow Design | **100% dynamic** — no hardcoded year logic; all workflows adapt to dataset |
| 📦 Deliverable | **2 end-to-end analytical modules** covering production trends and innovation lifecycle |

---

## 🎯 Business Problem

The EV industry between 2010 and 2024 is not a smooth growth curve — it is a story of explosive surges, sudden collapses, strategic pauses, and deliberate relaunches.

**Without structured lifecycle analysis, this data looks like noise. This project turns it into signal.**

**5 questions that drive the analysis:**

1. Which years saw the **largest production increases** — and which saw the sharpest collapses?
2. Which EV models **went silent for years** before making a confirmed comeback — and how long were they gone?
3. Which years drove the most **new model introductions**, and which manufacturers led innovation surges?
4. When did **model extinction** peak — and what does that tell us about market consolidation?
5. What separates a **temporary production pause** from a permanent discontinuation?

---

## 🔍 Key Insights — 15 Years of EV Market Intelligence

### 📈 Production Volatility (2010–2024)
- **15 consecutive years** of production data analyzed using sequential multi-row YoY calculations — no manual formula inputs, fully pipeline-driven
- Identified the **single year with the largest absolute production increase** — the inflection point where the EV market transitioned from niche to mainstream
- Identified the **single year with the sharpest production decline** — revealing market stress points driven by supply chain disruption, policy shifts, or competitive consolidation
- YoY delta analysis exposed that **growth was not linear** — the market moved in distinct phases: early experimentation, rapid acceleration, volatility, and consolidation

### 🔄 Production Gap & Comeback Analysis
- **Top 3 models with the longest confirmed production pauses** were ranked — models that disappeared from the market for multiple years before returning
- Gap detection used **grouped multi-row sequential logic** in Alteryx to measure exact pause durations per make-model combination — no SQL, no Python, pure workflow
- Findings reveal that **long pauses were strategic, not accidental** — models that returned after 3+ year gaps often came back repositioned (different segment, updated specs, new pricing tier)
- This distinguishes **genuine product strategy** (planned pause → relaunch) from **product failure** (discontinuation)

### 🚀 Innovation Surge Analysis
- **First-appearance detection** was applied across all 50+ models to identify the exact year each new EV model entered production
- Identified the **peak innovation year** — the single year with the highest number of new model introductions across the dataset
- **Manufacturer-level breakdown** revealed that innovation surges were driven by a small number of OEMs introducing multiple new models in the same year — a classic platform-launch strategy
- Peak innovation windows were followed by **market thinning** — fewer new introductions in subsequent years as manufacturers consolidated their lineups

### ☠️ Model Extinction Patterns
- **Extinction events** defined as: model present in year Y, absent in year Y+1 with no subsequent return
- Identified the **year with the highest model extinction rate** — revealing when competitive pressure or internal portfolio decisions forced the largest wave of discontinuations
- Cross-referencing extinction years with innovation years shows a clear **creative destruction pattern**: high innovation entry → competitive pressure → high extinction of weaker models
- This lifecycle behavior mirrors product portfolio theory — **introduction, growth, maturity, decline** — mapped empirically from real production records

---

## 🏗️ Analytical Architecture — 2-Module Workflow Design

```
📦 EV Production Lifecycle Analysis
│
├── 🔹 MODULE 1: Production Trends & Model Comeback Analysis
│   │
│   ├── INPUT: Raw EV production records (2010–2024)
│   │
│   ├── STEP 1 → Filter: Scope to 2010–2024 (exclude partial 2025 records)
│   │
│   ├── STEP 2 → Summarize: Aggregate total production count by year
│   │
│   ├── STEP 3 → Multi-Row Formula: Sequential YoY delta calculation
│   │            (Row[0].Count − Row[-1].Count) — fully dynamic, no hardcoding
│   │
│   ├── STEP 4 → Sort + Sample: Isolate MAX increase year & MAX decrease year
│   │
│   ├── STEP 5 → Grouped Multi-Row Formula: Gap detection per make-model
│   │            → Detect year gaps → Measure pause duration → Confirm comeback
│   │
│   └── OUTPUT: YoY production trend + Top 3 longest comeback models ranked
│
└── 🔹 MODULE 2: Innovation & Model Extinction Analysis
    │
    ├── INPUT: Same raw EV production dataset
    │
    ├── STEP 1 → First-Appearance Detection: Min year per make-model = introduction year
    │
    ├── STEP 2 → Summarize by year: Count new introductions per year
    │
    ├── STEP 3 → Sort + Sample: Identify peak innovation year + manufacturer breakdown
    │
    ├── STEP 4 → Year-over-year existence comparison: Present in Y, absent in Y+1?
    │
    ├── STEP 5 → Summarize extinct models per year → Identify peak extinction year
    │
    └── OUTPUT: Innovation timeline + Extinction heatmap by year
```

---

## 🛠️ Alteryx Workflow — Tools Used

| Alteryx Tool | Purpose in This Project |
|---|---|
| **Filter** | Scope dataset to 2010–2024; exclude incomplete 2025 records |
| **Sort** | Order records chronologically for sequential logic to function correctly |
| **Summarize** | Aggregate production counts by year and by make-model |
| **Multi-Row Formula** | Core YoY delta logic — accesses previous row values dynamically |
| **Formula** | Derived fields — gap flags, innovation flags, extinction flags |
| **Sample** | Extract top N results (e.g., Top 3 comeback models, peak year) |
| **Union** | Merge analytical outputs from parallel workflow branches |
| **Select** | Field cleanup and output schema management |

> **Design Principle:** Zero hardcoded years. Every threshold, ranking, and filter is derived from the data itself — making this workflow reusable on any future dataset update.

---

## 📊 Workflow & Output Previews

### Module 1 — Production Trends & Comeback Detection
![Workflow Part 1A](Screenshot%202026-02-06%20233212.png)
![Workflow Part 1B](Screenshot%202026-02-06%20233305.png)
![Output — YoY Production Trend](Screenshot%202026-02-06%20233445.png)
![Output — Top 3 Comeback Models](Screenshot%202026-02-06%20233513.png)
![Output — Gap Duration Ranked](Screenshot%202026-02-06%20233546.png)
![Output — Largest Increase & Decrease Years](Screenshot%202026-02-06%20233622.png)
![Output — Summary View](Screenshot%202026-02-06%20233649.png)

### Module 2 — Innovation & Extinction Analysis
![Workflow Part 2A](Screenshot%202026-02-07%20235235.png)
![Output — Peak Innovation Year](Screenshot%202026-02-07%20235313.png)
![Output — Manufacturer Innovation Breakdown](Screenshot%202026-02-07%20235406.png)
![Output — Model Extinction by Year](Screenshot%202026-02-07%20235829.png)

---

## 💼 Skills Demonstrated (Recruiter Checklist ✅)

- ✅ **Enterprise ETL Tool Proficiency** — Full Alteryx Designer workflow built end-to-end (Alteryx Designer Core Certified)
- ✅ **Time-Series Analysis** — 15-year sequential YoY delta computation using Multi-Row Formula logic
- ✅ **Lifecycle Analytics** — Production gap detection, comeback confirmation, extinction classification
- ✅ **Innovation Tracking Framework** — First-appearance detection across 50+ models and multiple OEMs
- ✅ **Dynamic Workflow Design** — Zero hardcoded values; fully reusable and scalable pipeline
- ✅ **Business Problem Framing** — Raw production records translated into strategic market lifecycle narrative
- ✅ **Modular Architecture** — 2 independent analytical modules that together form a complete study
- ✅ **Structured Output Design** — Each workflow branch produces a clean, ranked, decision-ready result

---

## 📁 Repository Structure

```
📂 EV-Production-Lifecycle-Analysis/
│
├── 📦 EV Data Preparation Project.yxzp         # Module 1 — Alteryx workflow package
├── 📦 EV Data Preparation Project Part 2.yxzp  # Module 2 — Alteryx workflow package
├── 📊 eletric vehicles.xlsx                     # Raw EV production dataset (2010–2024)
│
├── 🖼️ Screenshot 2026-02-06 233212.png          # Module 1 workflow view
├── 🖼️ Screenshot 2026-02-06 233305.png          # Module 1 workflow continued
├── 🖼️ Screenshot 2026-02-06 233445.png          # YoY production trend output
├── 🖼️ Screenshot 2026-02-06 233513.png          # Top 3 comeback models output
├── 🖼️ Screenshot 2026-02-06 233546.png          # Gap duration ranked output
├── 🖼️ Screenshot 2026-02-06 233622.png          # Largest increase & decrease output
├── 🖼️ Screenshot 2026-02-06 233649.png          # Summary output view
├── 🖼️ Screenshot 2026-02-07 235235.png          # Module 2 workflow view
├── 🖼️ Screenshot 2026-02-07 235313.png          # Peak innovation year output
├── 🖼️ Screenshot 2026-02-07 235406.png          # Manufacturer innovation breakdown
├── 🖼️ Screenshot 2026-02-07 235829.png          # Model extinction by year output
│
└── 📄 README.md                                 # This file
```

---

## 🏅 Certification

This project was built using **Alteryx Designer** — the industry-standard ETL and advanced analytics platform used by Fortune 500 data teams globally.

![Alteryx](https://img.shields.io/badge/Alteryx_Designer_Core-Certified-0078D4?style=for-the-badge&logo=alteryx&logoColor=white)

---

## 👤 About the Author

**Adhitya Yellapu** — Data & Business Operations Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adhitya-yellapu)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ADHITYAYELLAPU)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://adhityayellapu.github.io/Portfolio/)

---

*Self-initiated project designed to demonstrate enterprise-level time-series and lifecycle analytics using Alteryx Designer — the kind of analysis performed by data teams at automotive OEMs, EV consultancies, and energy analytics firms tracking global electrification trends.*
