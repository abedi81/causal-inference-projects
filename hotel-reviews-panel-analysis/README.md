# Hotel Reviews and Rating Dynamics: A Panel Data Analysis

## Overview

This project analyzes how online review volume and review sentiment (positive and negative words) influence hotel ratings using a large-scale panel dataset from Booking.com.

The goal is not only to identify whether reviews matter, but to quantify **how much they matter** and whether negative and positive feedback have asymmetric effects.

---

## Data

- Source: Booking.com reviews dataset  
- Observations: ~270,000 hotel-month observations  
- Structure: Panel data (hotel-level over time)

---

## Methods

To ensure robust and reliable results, multiple econometric models were applied:

- Pooled OLS  
- Fixed Effects (Hotel and Time)  
- Dynamic Panel GMM (Arellano-Bond / System GMM)  

These methods allow us to:
- Control for unobserved hotel characteristics  
- Account for time-specific shocks  
- Address potential endogeneity  

---

## Key Findings

- **Negative review content has a stronger impact on ratings than positive content**
- Increasing negative word counts significantly reduces hotel ratings
- Positive reviews improve ratings, but with a smaller magnitude compared to negative effects

👉 This suggests that:
Hotels should prioritize **reducing negative customer experiences**, not only increasing positive reviews.

---

## Business Insight

Even small increases in negative feedback can lead to measurable declines in ratings, which may impact:

- Customer trust  
- Booking decisions  
- Revenue (if linked with demand)

This framework can be extended to estimate the **financial impact of reviews** if revenue or occupancy data is available.

---

## Files

- `hotel-review-causal-analysis.ipynb` → Full analysis and code  
- `hotel-review-causal-analysis.html` → Clean report version  

---

## Skills Demonstrated

- Causal inference  
- Panel data econometrics  
- Fixed effects modeling  
- Dynamic panel GMM  
- Data analysis and interpretation  
- Translating statistical results into business insights

