# Player Behavior & Churn Prediction Pipeline

## Project Overview
In the highly competitive iGaming industry, retaining players is significantly more cost-effective than acquiring new ones.  
This project delivers an end-to-end Predictive Analytics Pipeline designed to identify early churn signals before players disengage from the platform.

By analyzing behavioral friction, engagement velocity, and value indicators, the pipeline produces a proactive, CRM-ready list of high-risk players, enabling targeted retention interventions.

---

## Business Objectives
- **Predict Churn:** Identify players likely to become inactive within the next 7 days
- **Isolate Friction:** Quantify the impact of payment failures on player retention
- **Enable Action:** Segment at-risk players by churn driver 
  - Technical (payment friction)  
  - Engagement (declining activity)
- **Optimize Spend:** Improve ROI of loyalty and retention campaigns

---

## Tech Stack & Methodology
- **Python:** Pandas, NumPy, Scikit-Learn, Seaborn  
- **Machine Learning:** Random Forest Classifier (Recall-optimized)
- **Statistical Analysis:** Feature importance ranking & probability analysis
- **CRM Integration:** Automated CSV generation for high-risk player targeting

---

## Behavioral Feature Engineering & EDA
To simulate real-world conditions, I generated a messy, event-style dataset resembling production iGaming logs.  
Feature engineering focused on three core behavioral dimensions:

- **Frequency:** Login count & engagement consistency
- **Friction:** Payment failure rate
- **Value:** Average bet size

### Key Insight — The Player “Breaking Point”
Quantitative analysis revealed a clear threshold where patience collapses:

- **Friction Multiplier:**  
  Churned players experienced 3.61× higher payment failure rates
- **Engagement Gap:**  
  Active players logged in 2.1× more often 
  - Median logins: 85 (active)** vs 33 (churned)

**Insight:**  
Players don’t simply “get bored” — technical friction in the deposit funnel is the primary churn catalyst.

---

## Machine Learning Model (Random Forest)
A Random Forest Classifier was trained to automate churn detection.  
Given the retention use case, Recall was prioritized to ensure minimal false negatives — acting as a safety net for at-risk players.

### Model Performance

| Metric | Score | Business Interpretation |
|------|------|--------------------------|
| Recall (Churn Class) | 94% | Successfully identified 94% of all actual churners |
| Precision (Churn Class) | 77% | Majority of flagged players were truly at risk |
| Overall Accuracy | 90% | Strong, reliable performance across the player base |

---

## Feature Importance — The “Why”
The model ranked churn drivers by influence:

- Total Logins (39.7%)  
  Strongest signal of long-term engagement
- Payment Failure Rate (37.9%)  
  Confirms technical friction destroys player LTV
- Average Bet Size (22.2%)  
  Secondary indicator of declining interest

---

## Business Impact & Recommendations
- **Proactive Retention:**  
  Enables CRM teams to target players with 90%+ churn probability before exit
- **Friction Reduction:**  
  Recommend automated engineering alerts when a player exceeds a 15% payment failure rate, regardless of VIP status
- **Revenue Protection:**  
  Identifying 94% of churners helps safeguard an estimated 12–15% of monthly revenue previously lost to silent exits

---
