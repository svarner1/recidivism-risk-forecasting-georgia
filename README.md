# recidivism-risk-forecasting-georgia

# 🏛️ Recidivism Risk Forecasting & Rehabilitation Strategy (Georgia)
**Google Data Analytics Capstone Case Study**  
**Author:** Sydney Varner  
**Tools:** Python (Pandas, NumPy), SQL, Google Sheets, Google Docs  
**Data Sources:** National Institute of Justice (NIJ) Recidivism Challenge (25,373 records), Georgia Department of Corrections (GDC) CY/FY Reports

---

## 📌 Executive Summary
This project analyzes 3-year post-release outcomes for over 25,000 individuals released from Georgia state prisons. By synthesizing individual-level behavioral indicators with 10-year systemic facility performance data, this case study identifies the highest-leverage intervention strategies to reduce reoffending.

### Key Findings
1. **Employment is the Strongest Reentry Shield:** Sustained employment (>75% of days) reduces 3-year recidivism from **67.2% down to 43.6%** (a 23.6 percentage point drop).
2. **Rehabilitation Requires a 10+ Dosage Threshold:** Attending 1–3 program sessions yields higher recidivism (~66%) due to mandate dropouts, but completing **10 or more sessions drops recidivism to 47.1%**.
3. **Absconding Outweighs Relapse as a Risk Signal:** Individuals with missing drug test records reoffend at **67.6%**, higher than individuals testing positive for narcotics (**62.2%**), proving that non-reporting is the primary behavioral early-warning indicator.
4. **Transition Centers Cut Reconviction by Over 50%:** GDC Transition Centers recorded a **12.3% reconviction rate in 2022** (10-year mean: **17.2%**) compared to **31.1%** for standard inmate facilities and **33.8%** for state prisons.

---

## 🛠️ Data Pipeline & Process
- **Data Hygiene:** Avoided listwise deletion (`dropna()`), which would have eliminated >20% of high-risk records; engineered a custom 3-tier substance use status (`np.select`).
- **Feature Engineering:** Discretized continuous employment into 5 tiers (`pd.cut`) and validated legal work exemptions with `pd.crosstab`.
- **Multi-Tab Reporting:** Automated compilation of clean summary tables into `Recidivism_Case_Study_Summary.xlsx` using `pd.ExcelWriter`.

---

## 📊 Visualizations & Dashboards
![Recidivism Rate vs. Drug Test Status Graph](<Recidivism Rate vs. Drug Test Status.png>)
![Headcount vs. Drug Test Status Graph](<Headcount vs. Drug Test Status.png>)
![Recidivism Rate vs. Employment Group Graph](<Recidivism Rate vs. Emplpoyment Group.png>)
![10-year Recidivism Ranges vs. Recent & Average Rates Graph](<10-year Recidivism Ranges vs. Recent & Average Rates.png>)


---

## 🎯 Policy & Business Recommendations
- **Shift Capital to Transition Centers:** Transition beds cost less and cut reconviction in half.
- **Pay for Retention, Not Enrollment:** Contract rehabilitation providers based on 10+ session completion rates.
- **Automated Check-in Alerts:** Treat missed drug screens as immediate field outreach opportunities rather than punitive violations.
