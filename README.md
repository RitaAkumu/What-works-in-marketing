# 📊 What Works in Marketing? — Campaign Effectiveness Analysis

> An end-to-end analysis of marketing campaign response data to identify high-value customer segments, behavioural drivers of response, and a predictive logistic regression model for smarter campaign targeting.

**Author:** Rita Akumu &nbsp;|&nbsp; **Date:** March 2026 &nbsp;|&nbsp; **Tools:** Python · Excel / Power BI

---

## 📌 Project Overview

Most marketing campaigns reach everyone — but resonate with very few.

This project investigates **why only 15% of customers respond** to marketing campaigns and builds a data-driven framework for identifying *who* is most likely to respond, *what* drives that behaviour, and *how* organisations can improve their return on marketing investment (ROMI).

The analysis moves through 8 structured phases — from baseline response profiling to predictive modelling and actionable segmentation strategy.

---

## 🎯 Objectives

- Quantify overall marketing response rates and assess class imbalance
- Evaluate acceptance rates across 5 individual campaigns (Cmp1–Cmp5)
- Identify how response varies by customer income, age, household structure, and marital status
- Compare responders vs non-responders on total spending behaviour (MntTotal)
- Assess whether prior campaign acceptance predicts future response
- Analyse the effect of purchase channels (web, catalog, store) on response likelihood
- Train and evaluate a logistic regression model using AUC, precision, and recall
- Translate findings into actionable targeting and segmentation recommendations

---

## 🗂️ Repository Structure

```
├── data/
│   └── marketing_data.csv          # Raw dataset
├── notebooks/
│   └── marketing_analysis.ipynb    # Full analysis notebook (Python)
├── visuals/
│   └── *.png                       # Charts and visualisations (Power BI / Excel exports)
├── report/
│   └── What_Works_in_Marketing.pdf # Styled full report
└── README.md
```

---

## 🔍 Key Findings

### 1. Overall Response Rate
- Only **15% of customers** responded to marketing campaigns
- The majority (79.2%) accepted **zero** campaigns, highlighting a heavily imbalanced outcome variable

### 2. Campaign Performance
| Campaign | Acceptance Rate |
|----------|----------------|
| Campaign 1 | 6.44% |
| Campaign 2 | 1.36% ❌ Worst |
| Campaign 3 | 7.39% |
| **Campaign 4** | **7.44% ✅ Best** |
| Campaign 5 | 7.30% |

### 3. Spending Behaviour — Strongest Driver
Spending is the single most powerful predictor of campaign response:

| Spend Band | Response Rate |
|------------|--------------|
| 1 (Lowest) | 5.5% |
| 2 | 10.9% |
| 3 | 11.1% |
| 4 | 22.5% |
| **5 (Highest)** | **43.1%** |

> 💡 High-value customers (Band 5) are **8x more likely** to respond than the lowest spenders.

### 4. Income
- Response rates are flat (~11–12%) across the bottom 75% of earners
- A sharp jump appears at the **top 10% income band (~40% response rate)**
- Chi-square test: statistically significant (p < 0.001), Cramér's V = 0.19 (weak-to-moderate)

### 5. Prior Campaign Acceptance
- Customers who accepted previous campaigns are the **strongest predictor** of future response
- Repeat responders form a core high-converting segment despite being a small minority

### 6. Demographics — Limited Predictive Power
- **Age:** Modest variation (12.6%–17.3%) — not a strong predictor
- **Household composition:** Customers without children respond more, but weak effect overall
- **Marital status:** Statistically significant but Cramér's V = 0.013 — extremely weak practical effect
- **Complaints history:** No association (chi-square p = 0.961)

---

## 🤖 Model Performance

A **Logistic Regression** model was trained on an 80/20 stratified split.

| Metric | Score |
|--------|-------|
| Accuracy | 87% |
| **Precision** | **0.72** |
| Recall | 0.29 |
| **AUC** | **0.86** |

- The **high AUC (0.86)** confirms strong ability to distinguish responders from non-responders
- **Precision of 0.72** means 72% of customers predicted to respond actually do — strong signal for targeted outreach
- Lower recall is acceptable when the goal is **precision-driven budget allocation**, not full coverage

---

## 💡 Recommendations

1. **Target top spending segments (Bands 4 & 5)** — highest ROI, lowest wasted spend
2. **Prioritise repeat responders** — enroll in loyalty or VIP campaigns
3. **Use predicted probability scores** to rank customers; target top 20–30% only
4. **Invest in digital/web channels** — statistically significant association with response
5. **Avoid broad mass campaigns** — 85% non-response rate makes them inefficient by default

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Python** | Data cleaning, EDA, statistical testing, logistic regression modelling |
| **Pandas / NumPy** | Data manipulation and aggregation |
| **Scikit-learn** | Model training, evaluation (AUC, precision, recall) |
| **Matplotlib / Seaborn** | Exploratory visualisations |
| **Excel / Power BI** | Campaign-level dashboards and visual reporting |

---

## 📄 Full Report

The complete styled report is available in the `/report` folder:
👉 [`What_Works_in_Marketing.pdf`](./report/What_Works_in_Marketing.pdf)

---

## 👩‍💻 Author

**Rita Akumu** — Data Analyst  
📧 ritaakumu20@gmail.com &nbsp;|&nbsp; 🔗 [https://www.linkedin.com/in/rita-akumu-] &nbsp;|&nbsp; 

---

*This project is part of my data analytics portfolio. Feel free to explore, fork, or reach out with questions!*
