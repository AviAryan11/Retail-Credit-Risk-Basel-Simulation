# Retail-Credit-Risk-Basel-Simulation
End-to-end retail credit risk analytics and Basel capital impact simulation using real LendingClub loan data.
# Retail Credit Risk & Basel Capital Simulation

## Project Overview

This project develops an end-to-end retail credit risk analytics model using real LendingClub loan data (2016–2017, 167K resolved loans).

The objective was to:
- Estimate historical Probability of Default (PD)
- Model Expected Loss (EL) using PD × LGD × EAD framework
- Identify portfolio concentration risk
- Perform stress testing using dynamic PD shocks
- Simulate Basel-style Risk Weighted Assets (RWA) and Capital Adequacy Ratio (CAR) impact

---

## Dataset

Source: LendingClub Loan Data (Kaggle)

- 167,000 resolved loans (Fully Paid / Charged Off)
- Variables analyzed:
  - Credit grade
  - Debt-to-Income ratio (DTI)
  - Annual income
  - Revolving utilization
  - Loan amount

Current and unresolved loans were excluded to avoid censoring bias in PD estimation.

---

## Methodology

### 1. Probability of Default (PD)

Historical PD calculated as:

PD = Total Defaults / Total Loans

PD was segmented by:
- Credit grade
- DTI buckets
- Income buckets
- Revolving utilization buckets

---

### 2. Expected Loss (EL)

EL = PD × LGD × EAD

Assumptions:
- LGD = 40% (unsecured retail lending)
- EAD proxied by loan amount

---

### 3. Stress Testing

A dynamic stress parameter was implemented using Power BI What-If functionality.

PD Stress Scenario:
- Adjustable from 0% to 100%

Stressed Expected Loss recalculates dynamically.

---

### 4. Basel Capital Simulation

Simplified regulatory framework:

CAR = Capital / RWA

Where:
- Capital assumed fixed at 300M
- RWA = Exposure × Dynamic Risk Weight
- Risk weight increases under stress

This allows simulation of capital deterioration under adverse scenarios.

---

## Key Insights

- Mid-grade exposures (Grade C) contributed most to portfolio loss due to exposure concentration.
- DTI demonstrated stronger discriminatory power than income in predicting default.
- Stress scenarios significantly increased Expected Loss and reduced CAR.
- Portfolio risk is driven by both credit quality and exposure concentration.

---

## Tools Used

- Power BI
- DAX
- Risk Modeling Concepts (PD, LGD, EAD)
- Basel III Capital Framework

---

## Future Improvements

- Logistic regression-based PD modeling
- ROC/AUC model validation
- Nonlinear IRB-style RWA calculation
- Macro-linked stress scenarios
