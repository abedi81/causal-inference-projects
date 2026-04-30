# A/B Testing Analysis: Causal Impact of Advertising on User Conversion

## Overview

This project evaluates the causal impact of advertising on user conversion using a structured A/B testing framework.

The objective is not only to determine whether ads increase conversion, but also to understand **when they are most effective**, **for whom they work best**, and whether the results are **statistically and causally reliable**.

---

## Methodology

The analysis combines experimental design with multiple estimation strategies to ensure robustness and interpretability.

### Estimation Approaches

- **Average Treatment Effect (ATE)**  
- **Linear Probability Model (LPM)**  
- **Logistic Regression (Average Marginal Effects)**  

These complementary methods provide consistent estimates of the causal impact of advertising.

---

## Heterogeneity Analysis

To understand variation in treatment effects:

- **Within-treatment behavior** was analyzed across:
  - Hour of day  
  - Day of week  

- **Conditional Average Treatment Effects (CATE)** were estimated to identify segments where advertising is more or less effective.

---

## Robustness Checks

To validate the causal interpretation, several robustness checks were conducted:

- **Permutation tests** → verify results are not driven by random chance  
- **Placebo tests** → ensure no spurious treatment effects  
- **Subsampling (balanced groups)** → confirm results are not due to sample imbalance  

---

## Key Findings

- Advertising increases conversion by approximately **0.7–0.9 percentage points**
- The effect is **statistically significant and economically meaningful**
- Conversion rates vary substantially by **time of day**
  - Afternoon and early evening perform best
- **Treatment effects are heterogeneous**
  - Stronger effects observed at specific hours
  - Limited variation across days of the week

---

## Business Insight

- Advertising is effective, but **timing is critical**
- Optimizing ad delivery by **hour of day** can significantly improve performance
- Even small increases in conversion (≈0.8pp) can translate into **meaningful revenue gains at scale**



---

## Skills Demonstrated

- A/B testing and experimental design  
- Causal inference  
- Treatment effect estimation (ATE, CATE)  
- Logistic and linear modeling  
- Hypothesis testing and robustness validation  
- Translating statistical results into business insights
