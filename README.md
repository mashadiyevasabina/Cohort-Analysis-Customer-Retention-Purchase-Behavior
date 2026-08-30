# 📜 Cohort Analysis: Customer Retention & Purchase Behavior
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1tgjxNQR4SXMQD0x6nGKyuD6WoawJP4ol)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-3776AB.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📊 Project Overview
This project performs a comprehensive **Cohort Analysis** on e-commerce sales data to evaluate customer retention, purchase patterns, revenue trends, and Average Revenue Per User (ARPU). The analysis spans transactions from **October 2020 to September 2021**.

### 🎯 Key Business Questions
* When were customer acquisition and revenue at their peak?
* How quickly does customer activity decline after the initial purchase?
* What percentage of customers return for a second purchase?
* How does revenue per active customer (ARPU) evolve over time?
* What retention strategies can improve long-term Customer Lifetime Value (CLV)?

---

## 🧹 Data Pipeline & Preparation
* **Data Source:** `sales.csv` (286,392 rows, 33 columns).
* **Completed Transactions:** Filtered for `status == "complete"` to measure true realized revenue.
* **Date Standardization:** Converted `order_date` (`DD-MM-YYYY`) to `datetime64[ns]` format.
* **Deduplication:** Identified and removed 3,233 duplicate rows.
* **Revenue Calculation:** Applied `Revenue = (price * qty_ordered) - discount_amount`.

---

## 📈 Monthly Cohort & ARPU Summary

### Core Monthly Cohorts Overview
| Cohort | Unique Orders | Unique Customers | Total Revenue | Key Observation |
| :--- | :--- | :--- | :--- | :--- |
| **2020-10** | 5,273 | 1,444 | ~$8.62M | Baseline acquisition month |
| **2020-11** | 6,584 | 2,321 | ~$11.25M | Moderate growth period |
| **2020-12** | 30,807 | 13,184 | ~$68.09M | **Peak acquisition & revenue spike** |

> 📌 **Key Insight:** December 2020 represents a major outlier in customer acquisition and volume, likely driven by holiday seasonality, promotional campaigns, or year-end sales.


### 💰 ARPU & Retention Formulas
* **Average Revenue Per User:** 
  $$\text{ARPU} = \frac{\text{Cohort Revenue}}{\text{Active Customers}}$$
* **Retention Rate:** 
  $$\text{Retention Rate (\%)} = \left( \frac{\text{Active Customers at Lifetime } N}{\text{Initial Cohort Size}} \right) \times 100$$
* **Cumulative Churn:** 
  $$\text{Cumulative Churn} = 1 - \text{Retention Rate}$$

---

## 📉 Key Analytical Findings

1. **Sharp Drop after Acquisition:** Retention drops significantly after Week 0/Month 0 (Week 1 retention drops to low single digits for mature cohorts).
2. **First-to-Second Purchase Gap:** A massive portion of acquired users never complete a second transaction.
3. **Monetization vs. Volume:** High ARPU periods do not always reflect customer loyalty; they are often driven by seasonal high-value baskets or product mix.

---

<img width="1065" height="547" alt="Screenshot 2026-08-30 220047" src="https://github.com/user-attachments/assets/d7318835-2920-42be-a829-c96f40c43f36" />


## 💡 Strategic Business Recommendations

* **Optimize Second-Purchase Conversion:** Focus on immediate post-purchase onboarding, win-back emails, and second-order discounts.
* **Reactivation Segmentation:** Target inactive users based on drop-off periods (30, 60, 90+ days).
* **Capitalize on Peak Periods:** Replicate the marketing and discount conditions of the December 2020 campaign.
* **Cohort-Based Marketing:** Shift from generic blast campaigns to cohort lifecycle triggers.

---

## 🧪 Next Steps & Extensions
* [ ] Integrate **RFM (Recency, Frequency, Monetary)** Segmentation.
* [ ] Calculate predictive **Customer Lifetime Value (LTV)** models.
* [ ] Evaluate retention by **Marketing Acquisition Channel** and **Product Category**.

---

## 📁 Project Structure
```text
cohort-analysis/
│
├── Cohort_Analysis.ipynb
├── sales.csv
├── README.md
└── images/
    ├── monthly_cohort_summary.png
    ├── customer_retention_heatmap.png
    ├── arpu_heatmap.png
    └── weekly_retention_heatmap.png
