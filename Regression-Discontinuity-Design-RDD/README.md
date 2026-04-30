# Regression Discontinuity Design: Impact of Legal Drinking Age on Mortality

## Overview

This project replicates a well-known study examining the causal impact of legal access to alcohol at age 21 on mortality rates among young adults in the United States.

The key idea is that turning 21 provides legal access to alcohol, which may increase risky behaviors such as drunk driving and alcohol-related accidents. If this is true, we should observe a sudden increase in mortality exactly at age 21.

The goal is to estimate this causal effect using Regression Discontinuity Design (RDD).

---

## Methodology

The analysis uses age as a continuous running variable:

- **Running variable:** Age  
- **Cutoff:** 21 years  
- **Treatment:** Legal access to alcohol  
- **Outcome:** Mortality rate  

### Identification Strategy

Individuals just below and just above age 21 are assumed to be very similar in all respects except for legal access to alcohol.

Therefore, any sudden jump in mortality at age 21 can be interpreted as a causal effect.

---

## Estimation Approaches

### 1. Local Polynomial Regression

- Estimates separate trends on either side of the cutoff  
- Allows for flexible relationships between age and mortality  
- Captures the discontinuity at age 21  

---

### 2. Alternative Functional Forms

- Models with different slope assumptions are tested:
  - Flexible models (different trends on each side)  
  - Constrained models (same trend, only a jump at the cutoff)  

 This ensures results are not driven by modeling choices  

---

## Heterogeneity Analysis

The analysis focuses on **local effects near the cutoff**:

- Estimates apply to individuals around age 21  
- Effects represent a **Local Average Treatment Effect (LATE)**  

 This reflects the causal impact for individuals affected by the policy change  

---

## Robustness Checks

- Estimation across multiple bandwidths:
  - Narrow windows (closer to cutoff)  
  - Wider windows (more observations)  

- Comparison across model specifications  

 This evaluates sensitivity to:
- Window size  
- Functional form  

---

## Key Findings

- There is a clear and statistically significant increase in mortality at age 21  
- Estimated effects are stable across different bandwidths (approximately 0.08–0.10)  
- Confidence intervals remain tight and statistically significant  

 This provides strong evidence that legal access to alcohol increases mortality  

---

## Interpretation of Bandwidth Tradeoff

- **Narrow windows:**
  - More credible comparisons  
  - Higher variance (less precise estimates)  

- **Wider windows:**
  - More precise estimates  
  - Higher risk of bias  

 The stability of results across windows strengthens the credibility of the findings 
 Narrow and Wide window is like Bias and Variance trade-off in which **Narrow windows** has low bias and high variance which in machine learning model means the model might be precise but can not be applicable and flexible to different cases or various data and **Wider windows** means it has low precision or maybe the model might not have strong predictive power but it can be flexible for applying to different data. 

 We can conservatively say for causal purpose or decriptive purpose it might better to pay more attention to lower bias and for predictive purpose go for lower variance to make model applicable for diverse data. Yet, it depends on what we are studying. 

---

## Business / Policy Insight

- Policy changes can have immediate and measurable behavioral effects  
- Regression Discontinuity provides a powerful framework for evaluating such policies  
- Careful choice of bandwidth is critical for balancing bias and precision  

 This approach is applicable to:
- Policy thresholds  
- Eligibility rules  
- Business decision cutoffs
- Digital market reviews. 

---

## Skills Demonstrated

- Regression Discontinuity Design (RDD)  
- Local polynomial regression  
- Bandwidth selection and sensitivity analysis  
- Causal inference using quasi-experimental methods  
- Bias–variance tradeoff understanding  
- Translating statistical results into policy insights  
