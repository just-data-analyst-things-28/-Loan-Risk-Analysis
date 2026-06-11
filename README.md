#  Loan Portfolio Performance Dashboard

## Project Overview
This project presents an enterprise-grade **Loan Portfolio Analytics Framework** that evaluates the performance, exposure, and risk metrics of a vehicle loan portfolio across its entire lifecycle. 

Spanning a multi-page interactive dashboard, the framework tracks key credit performance indicators (KPIs), flags geographic concentrations, breaks down asset-class default exposures, and incorporates **Credit Vintage Curves (Static Pool Analysis)** and **Pool Amortization Profiles** to map loan pool decay and loss emergence over time.

---

## Technical & Business Architecture
The analysis is structured across five core dimensions of credit risk management:
1. **Delinquency & Risk Monitoring:** Tracking early-to-late stage delinquency buckets (Days Past Due - DPD) and directional trend lines.
2. **Portfolio Exposure & Composition:** Segmenting original and current loan exposure by geography (State-wise), asset type, vehicle make/brand, and loan purpose.
3. **Loss & Default Analysis:** Evaluating Key Risk Metrics including Loss Given Default (LGD), Loan-to-Value (LTV) ratios, Interest Rate structures, and Total Loss Amounts across defaulted assets.
4. **Static Pool Analytics:** Utilizing vintage-based tracking (by quarterly origination cohorts) to trace cumulative net losses relative to Months on Book (MOB).
5. **Amortization & Pool Decay:** Modeling the portfolio's structural pay-down rate through Pool Factor metrics over time.

---

## Portfolio High-Level KPIs

* **Total Loan Portfolio Size:** 500 Loans with an original pool balance of **546M** and a current total aggregate loan balance tracking at **3,276.44bn**.
* **Active Profile Base:** **385 Total Active Loans** currently active on books.
* **Portfolio Average Balance:** **805.46K** average current balance per active loan profile.
* **Portfolio-wide Delinquency Rate:** **55.00%** (aggregate portfolio tracking inclusive of running pools).
* **Average Ticket Pricing:** **11.01% Average Interest Rate** across the underwriting lifecycle.
* **Underwriting Risk Bounds:** **0.57 Average Loan-to-Value (LTV)** ratio at origination, demonstrating conservative asset backing despite running portfolio pressures.
* **Structural Lifespan:** **58.44 Months** Average Loan Term, with an **Average Remaining Term of 36.12 Months**.
* **Average Portfolio Ticket Size (EMI):** **25.85K** monthly equated installment.

---

## Detailed Component Breakdown & Business Insights

### 1. Delinquency Dynamics & Trend Analysis
* **Bucket Distribution:** The portfolio shows that **5.19K (87%)** of loan instances are tracking under **Current** standing. However, structural migration is visible in late-stage buckets: **0.49K (8%)** are classifying within early-to-mid delinquency buckets, and **0.07K (1%)** are trending toward advanced defaults.
* **Temporal Velocity:** The *Delinquency Trend Over Time* chart reveals a sharp, near-linear upward trajectory in delinquent loan counts moving from 2023 (~1K loans affected) into 2024 (breaching >5K instances).
* **Strategic Takeaway:** This indicates a systemic macroeconomic shock or aggressive underwriting expansion in late 2022/early 2023 that is currently seasoning out as severe delinquency. **Immediate collections intervention and vintage tightening are required.**

### 2. Composition & Geographic Exposure
* **Geographic Concentrations:** Portfolio risk exposure is heavily concentrated in specific regions. **Chhattisgarh** represents the single highest asset exposure (~48M Sum of Original Loan Amount), followed directly by **Madhya Pradesh** (~42M), **West Bengal** (~39M), and **Goa** (~38M).
* **Asset & Brand Diversification:** The vehicle make distribution is healthy and highly diversified, mitigating manufacturing-specific residual value risks:
  * **Hyundai:** 12.4% (62 Loans)
  * **Volkswagen:** 12.2% (61 Loans)
  * **Mahindra:** 10.4% (52 Loans)
  * **Skoda:** 10.2% (51 Loans)
  * **Kia / MG Motor:** 9.8% each (49 Loans each)
* **Loan Purpose:** The portfolio is dominated by **New Vehicle Purchases** (~0.48bn exposure), with minimal sub-allocations toward Used Vehicle Purchases (~0.04bn) and Refinance structures (~0.03bn).

### 3. Credit Risk, LGD & Asset Class Correlation
* **The Default Landscape:** **14 Total Defaulted Loans** have been realized, generating an aggregate **Total Loss Amount of 1M** with an **Average Loss Given Default (LGD) of 50.00%**.
* **Risk Pricing (LGD vs. Interest Rate):** A clear direct correlation exists between higher interest rates and elevated loss severity:
  * **SUVs** command both the highest aggregate Interest Rates (>1,250 combined score) and the highest LGD Estimates (~57%).
  * **Sedans** and **Compact SUVs** follow a linear mid-tier path (Interest Rate score ~1,100 to 1,170; LGD ~50% to 52%).
  * **MUVs** and **Hatchbacks** exhibit the lowest loss severity profiles (LGD ~46-47%) under lower yield baselines.
* **Collateral Protection (LTV Analysis):** **SUVs** and **MUVs** exhibit the highest average current Loan-to-Value profiles (~0.60), explaining the high LGD. Since these assets depreciate fast or are driven intensely, a default triggers a larger loss relative to the collateral recovery value.

### 4. Origination Volatility & Underwriting Calibration
* **Origination Down-Cycle:** Loan originations peaked in **2022 at 140 bookings**, followed by a contraction in **2023 (132 bookings)** and a severe deliberate tightening in **2024 (102 bookings)**. 
* **Strategic Alignment:** This contraction aligns with the surging delinquency curve noticed during the same period. The risk team successfully initiated a credit buy-back/tightening strategy to restrict exposures on high-risk vehicle segments.
* **Ticket Sizing Metrics:** **MUVs** and **SUVs** demand the highest payment burden with average EMIs sitting at **35K**, whereas entry-level **Hatchbacks** present a lower risk-to-income profile with an average EMI of **13K**.

### 5. Static Pool & Vintage Performance Analytics
* **Vintage Loss Curves:** Tracing cumulative net loss rates against **Months on Book (MOB)** reveals that losses typically peak early in the asset life cycle (between MOB 36 to 45, topping out at a **0.017 / 1.7%** cumulative rate) before stabilizing down to **0.002 / 0.2%** as the pool matures beyond MOB 12. 
* **Pool Amortization Velocity:** The pool factor amortization curve displays a textbook linear decay profile. It steps down predictably from **1.0 (origination balance)** to **0.52 by Month 23**, and reaches a residual pool factor of **0.23 by Month 35**. This fast principal repayment indicates strong structural liquidity support and a steady reduction in net credit exposure over a 3-year running window.

---

## Repository File Inventory

* `Delinquency and risk monitoring.png`: Dashboard capturing delinquency trend over time, bucket distribution (DPD buckets), and delinquency rates.
* `Portfolio Exposure and Composition.png`: Dashboard capturing geographic distributions (State-wise portfolio exposure), vehicle make pie-charts, and primary loan purposes.
* `Loss and Default Analysis.png`: Detailed asset-level risk reporting mapping LGD against underlying contractual coupon rates, defaulted loans, and LTV averages.
* `Loan Portfolio Performance.png`: Consolidated executive tracking view summarizing active loan KPIs, EMI breakdowns, and loan origination trends.
* `Static Pool Analysis.png`: Dynamic matrix charts mapping quarterly vintage cohorts across running asset loss curves and pool factor amortization profiles.

---

## How to Utilize this Framework
1. **Credit Policy Refinement:** Use the **LGD vs. Interest Rate** coordinates to implement risk-based pricing caps, specifically lowering max-allowable LTV limits on the SUV and MUV segments.
2. **Geographic Risk Triggers:** Leverage the state exposure data to temporarily down-scale underwriting limits in ultra-high exposure states like **Chhattisgarh** and **Madhya Pradesh** to avoid macroeconomic regional concentrations.
3. **Structured Provisioning:** Incorporate the **Vintage Loss Curves** directly into your **IFRS 9 / CECL Expected Credit Loss (ECL)** modeling frameworks to calculate Stage 1, 2, and 3 loan loss provisions based on actual historical MOB loss emergence.
