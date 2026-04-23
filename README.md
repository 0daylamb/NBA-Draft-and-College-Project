# NBA Draft and College Ranking Project
This repository covers an in-class final project for INST447 (Data Sources and Manipulation). This project explores if there is a relationship between an NBA players draft pick and if they went to a ranked school in one of the top conferences in the NCAA.

# 🏀 NBA Draft & College Basketball Prestige Analysis

> **Does attending a top-ranked program actually increase your chances of reaching the NBA?**  
> This project investigates the relationship between college basketball institutional prestige and professional draft outcomes — using data, statistics, and a healthy skepticism of conventional wisdom.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Research Questions](#research-questions)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Conclusions](#conclusions)
- [Reflections on AI Collaboration](#reflections-on-ai-collaboration)

---

## Overview

This project evaluates whether attending a **ranked college** or competing in a **powerhouse conference** (e.g., ACC, SEC) meaningfully increases a player's likelihood of being selected in the NBA Draft.

By merging historical NBA draft data with NCAA postseason and conference records from **2013 onward**, the study explores the degree to which institutional prestige predicts professional basketball outcomes — versus raw talent and individual performance.

---

## Research Questions

| # | Question |
|---|----------|
| 1 | **Ranking Impact** — Do colleges ranked in postseason play produce significantly more first-round picks? |
| 2 | **Unranked Success** — What is the draft distribution for players coming from unranked institutions? |
| 3 | **Conference Contribution** — Which NCAA conferences contribute the most players to the NBA? |
| 4 | **Predictive Value** — Does conference strength or college ranking independently predict draft selection? |

---

## Data Sources

All datasets were sourced from **[Kaggle](https://www.kaggle.com)**:

- 🏀 **NBA Historical Player Data** — Draft records including round, pick number, and college attended
- 🎓 **NCAA College Basketball Dataset** — Postseason rankings, conference affiliations, and season records (2013–present)

---

## Methodology

### Data Preparation

- **Merging**: NBA draft records were joined with NCAA postseason/conference data on college name
- **Normalization**: College names were standardized across datasets using **Python `re` (regex)** to resolve naming inconsistencies (e.g., `"UNC"` vs. `"North Carolina"`)
- **Cleaning**: Handled missing values, duplicate entries, and format discrepancies using **`pandas`**

### Statistical Tools

| Tool | Purpose |
|------|---------|
| **Chi-Square Test** | Assess association between postseason ranking and first-round draft selection |
| **Logistic Regression** | Estimate draft probability using binary predictors: *Ranked vs. Unranked* and *Major vs. Minor Conference* |

---

## Key Findings

### 1. 📉 Ranking ≠ First-Round Selection

> **Chi-Square Result:** $X^2 \approx 34.21$, $p \approx 4.95$

The chi-square test indicated **no statistically significant association** between a college's postseason ranking and first-round draft status. Despite the large test statistic, the corresponding p-value does not support rejecting the null hypothesis at conventional significance levels.

---

### 2. 🌟 Unranked Schools Punch Above Their Weight

> **Over 50%** of drafted players from unranked schools were selected in the **first round**.

This is a striking finding — it suggests that **individual performance and NBA scouting evaluations** regularly override institutional prestige when it comes to draft positioning.

<p align="center">
  <img src="https://github.com/0daylamb/NBA-Draft-and-College-Project/blob/3c215987478182b60ffbef8abd29a125330c99a7/Draft%20Round%20Distro%20for%20Unranked.png" width="600" alt="Draft Round Distribution for Unranked Schools"/>
</p>

---

### 3. 🏫 Conference Breakdown of NBA Draftees

| Conference | Share of Draftees |
|------------|:-----------------:|
| **ACC** | 23.3% |
| **SEC** | 20.6% |
| Other Major Conferences | Remaining share |

While the ACC and SEC produce the highest raw volume of drafted players, regression analysis revealed that **conference affiliation alone is not a statistically significant independent predictor** of being drafted.

<p align="center">
  <img src="https://raw.githubusercontent.com/0daylamb/NBA-Draft-and-College-Project/main/Top%20Conferences.png" width="600" alt="Top Conferences by NBA Draftees"/>
</p>

---

### 4. 📊 Regression Summary

Logistic regression using two binary predictors:

- `Ranked` (1) vs. `Unranked` (0)
- `Major Conference` (1) vs. `Minor Conference` (0)

**Neither predictor emerged as a significant independent driver of draft probability**, reinforcing the theme that talent scouting operates relatively independently of program prestige.

<p align="center">
  <img src="https://raw.githubusercontent.com/0daylamb/NBA-Draft-and-College-Project/main/Regression%20Plot.png" width="600" alt="Regression Plot"/>
</p>

---

## Conclusions

> 🏆 **Elite talent emerges from everywhere — not just traditional powerhouses.**

- Professional opportunities are **not strictly gatekept** by program prominence
- Individual performance and scouting evaluations **outweigh institutional standing** in draft decisions
- Conference prestige and postseason rankings offer **limited predictive value** as standalone signals

---

## Reflections on AI Collaboration

AI tools were used **intentionally and selectively** throughout this project:

- ✅ **Brainstorming** data normalization strategies (e.g., regex approaches for college name standardization)
- ✅ **Structuring** the logistic regression framework and variable selection

However, this project reinforced an important insight:

> *While AI is valuable for exploring methods, **human judgment remains essential** for diagnosing flaws in logic and ensuring data veracity.*

AI collaboration worked best as a thinking partner — not as a replacement for domain expertise and critical evaluation.

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-Statistical%20Testing-8CAAE6?logo=scipy&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Regression%20Analysis-4051A8?logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Data%20Visualization-11557C?logo=matplotlib&logoColor=white)
![Regex](https://img.shields.io/badge/re-Text%20Normalization-lightgrey?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)

---

*Data sourced from Kaggle | Analysis covers NCAA seasons 2013–present*
