Electric Vehicle Production Lifecycle & Market Dynamics Analysis (2010–2024) Using Alteryx

📌 Project Overview

This project analyzes electric vehicle (EV) production data to uncover long-term trends in growth, decline, innovation, and model lifecycle behavior across the EV market. Using Alteryx Designer, the analysis focuses on production volatility, model pauses and comebacks, new model introductions, and model extinction patterns between 2010 and 2024.

The project is structured as an end-to-end data preparation and analytical workflow, simulating how production and lifecycle insights are generated in real-world analytics and business environments.

🧠 What This Project Demonstrates

Strong data preparation and transformation skills

Advanced time-series and lifecycle analysis

Ability to translate raw data into business-relevant insights

Practical experience using enterprise analytics tools (Alteryx)

Clear, structured analytical thinking suitable for real-world roles.

🎯 Business Objectives

The primary objectives of this project are to:

Identify years with the largest increases and decreases in total EV production.

Detect EV models that experienced long production pauses followed by a confirmed return to production.

Analyze innovation cycles, including years with the highest number of newly introduced EV models.

Identify periods of model extinction, where models stopped production year-over-year.

Demonstrate strong data preparation, time-series logic, and lifecycle analysis using Alteryx.

📊 Dataset Description

Electric Vehicle Production Data

Fields used:

Model Year – Year of production

Make – Manufacturer / brand

Model – EV model name

Notes on data handling:

Only data from 2010 to 2024 is included in the analysis.

The year 2025 is excluded due to partial and incomplete records.

Each record represents a model produced in a given year.

🛠 Tools & Technologies

Alteryx Designer | Filter | Sort | Summarize | Multi-Row Formula | Formula | Sample | Union | Select

No hardcoded year logic was used; all workflows dynamically adapt to the dataset.

The analysis is divided into two analytical modules that together form a complete EV production lifecycle study.

🔹 Module 1: Production Trends & Model Comeback Analysis

This module focuses on production volatility and resilience.

Key analyses:

Year-over-year EV production change

Identification of the largest production increase and largest production decrease

Detection of EV models with production gaps, measuring the length of pauses before production resumed

Ranking of the top 3 models with the longest confirmed production pauses followed by a comeback

Key techniques:

Aggregation by year

Sequential (multi-row) year-over-year calculations

Grouped gap detection by make and model

🔹 Module 2: Innovation & Model Extinction Analysis

This module examines innovation and decline within the EV market.

Key analyses:

Identification of years with the highest number of newly launched EV models

Manufacturer-level breakdown of innovation surges

Detection of model extinction events, defined as models produced in year Y but not in Y+1

Identification of the year with the highest number of extinct models

Key techniques:

First-appearance detection for new models

Year-over-year existence comparison

Distinct model tracking and lifecycle logic

📈 Key Insights

EV production growth accelerated sharply in specific years, followed by noticeable declines in others, highlighting market volatility.

Several EV models experienced long production pauses before returning, indicating strategic repositioning rather than permanent discontinuation.

Innovation surged in select years, driven by a small number of manufacturers introducing multiple new models.

Periods of high innovation were often followed by increased model extinction, reflecting competitive market consolidation.

(Exact figures depend on the dataset version used.)
