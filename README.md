# AutoQA: Rubric Reliability & Predictive Usefulness Analysis 🤖📊

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458.svg)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-F7931E.svg)](https://scikit-learn.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()

## 📌 Project Overview
This repository contains a comprehensive data analysis project designed to evaluate an Automated Quality Assurance (AutoQA) system for educational lessons. The goal is to convert lesson transcripts into reliable, evidence-based teaching quality signals using Large Language Models (LLMs) and validate whether those signals predict meaningful student outcomes (Retention and Attendance).

This project demonstrates a closed-loop improvement workflow (**Detect → Route → Fix → Verify**) to scale teaching QA globally.

## 🎯 Business Objectives
1. **Measurement Reliability (Block 1):** Evaluate if AI models (GPT-4o vs. GPT-5.1) can measure pedagogical rubrics consistently, avoiding the "Agreement Trap" (high simple agreement due to severe class imbalance).
2. **Predictive Usefulness (Block 2):** Determine if the reliable AutoQA signals actually impact the company's bottom line—specifically predicting `m1_retained` (Month 1 Retention) and `next_lesson_attended`.

## 🛠️ Methodology & Tech Stack
* **Language:** Python
* **Libraries:** Pandas (Data manipulation, groupby aggregations), Matplotlib & Seaborn (Data visualization), Scikit-Learn (Cohen's Kappa, Accuracy metrics).
* **Techniques Used:**
  * **Statistical Reliability:** Calculated Cohen's Kappa ($\kappa$) to measure true inter-rater reliability between LLMs.
  * **Prompt/Rubric Engineering:** Rewrote ambiguous rubric items applying strict `COUNT ONLY IF` / `DO NOT COUNT` boundaries to make them calibration-grade and machine-readable.
  * **Predictive Analytics:** Applied cross-validation between model reliability ($\kappa$) and mean percentage lifts to discover true leading indicators of student engagement.

## 🚀 Key Findings
* **The "Agreement Trap":** Discovered that items with 99%+ simple agreement were actually statistically useless (Cohen's Kappa = 0.00) due to models defaulting to the majority class on autopilot.
* **Top Predictive Signals:**
  * **`item_3`:** Showed a massive **+25.7% lift** in Month 1 retention when performed correctly by the tutor.
  * **`item_14`:** Demonstrated an **18.2% lift** in next lesson attendance, paired with a solid moderate Kappa (0.54), making it a highly reliable and economically impactful signal.
* **Operational Strategy:** Designed a one-to-many automated workflow to route aggregated insights to Tutor Development, triggering async training campaigns instead of unscalable 1-on-1 interventions.

## 📂 Repository Structure
```text
├── data/
│   ├── autoqa_output_gpt4o_240.csv    # AutoQA output (Model Version A)
│   ├── autoqa_output_gpt51_240.csv    # AutoQA output (Model Version B)
│   └── outcomes_240.csv               # Student business outcomes
├── notebooks/
│   └── LuizFelipeBarros_AutoQA.ipynb  # Main analysis notebook (Data Cleaning, EDA, Stats)
├── docs/
│   └── AutoQA_Executive_Memo.pdf      # Executive summary of findings and business proposals
└── README.md
