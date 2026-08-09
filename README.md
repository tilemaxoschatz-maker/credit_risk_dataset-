# Credit Risk & Portfolio Analytics

## Overview
Analysis of 32,409 cleaned loan records to identify default drivers, quantify portfolio exposure,
and build a custom borrower risk-scoring framework.

## Structure
1. **Data Understanding & Cleaning** — missing values (median imputation), duplicates,
   impossible values (age/employment length caps), high-income review.
2. **Feature Engineering** — Debt_Burden_Score, Income_Category, Age_Group, Employment_Stability,
   Interest_Risk, Credit_Experience, Financial_Health_Score, Risk_Score, Risk_Segment,
   Expected_Loss, Exposure_Category, Young_High_Risk flag.
3. **Business Questions (40+)** — portfolio value, default rate, demographic/financial
   distributions, default-rate breakdowns, expected loss breakdowns, correlation analysis,
   outlier detection, top-risk borrower profiling.

## Key Constructed Metrics
- **Risk_Score**: composite of loan-to-income burden (40%), interest rate (40%), and
  inverse financial health (20%). Validated against actual default: Low Risk 4.5% default
  → Critical Risk 53.7% default.
- **Expected_Loss**: Risk_Score × loan_amnt — a simplified dollar exposure proxy, not a
  full PD×EAD×LGD model.
- **Financial_Health_Score**: weighted blend of income (50%), employment length (30%),
  and credit history length (20%), all min-max scaled.

## Known Limitations
- Component weights are judgment-based, not regression-derived.
- Risk_Score under-weights age's true (U-shaped) relationship with default.
- Expected_Loss is dominated by loan amount (0.95 correlation), not risk score (0.46).
- ~9.6% of loan_int_rate values are median-imputed.

## Dependencies
pandas, numpy, matplotlib, seaborn, scikit-learn (MinMaxScaler), scipy.stats (zscore),
statsmodels.

Author Tilemachos Chatzivasileiou

Mathematics Graduate | Aspiring Data Analyst

GitHub: https://github.com/tilemaxoschatz-maker

LinkedIn:https://www.linkedin.com/in/tilemachos-chatzivasileiou-1777ba400/
