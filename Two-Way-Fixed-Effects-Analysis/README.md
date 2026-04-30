# Beer Tax and Traffic Fatalities: A Two-Way Fixed Effects Analysis

## Overview

This project investigates whether higher beer taxes reduce traffic fatalities across U.S. states using panel data from 1982 to 1988.

The goal is to estimate the relationship between beer taxes and fatality rates while addressing potential bias caused by unobserved differences across states and over time.

The analysis applies a sequence of models, from simple regression to two-way fixed effects, to understand how controlling for different sources of variation affects the estimated impact.

---

## Methodology

The dataset consists of U.S. state-level panel data over multiple years.

### Key Variables:
- **Outcome:** Traffic fatality rate (fatalities per 10,000 people)  
- **Treatment:** Beer tax level  
- **Units:** U.S. states  
- **Time:** 1982–1988  

The main challenge is isolating the causal effect of beer taxes while accounting for differences across states and time.

---

## Estimation Approaches

### 1. Simple OLS Model

- Estimates the relationship between beer tax and fatality rate directly  
- Does not control for differences across states or time  
- Highly susceptible to **omitted variable bias**  

---

### 2. State Fixed Effects Model

- Controls for **time-invariant differences across states**  
  - Examples: road quality, culture, geography  
- Focuses on **within-state changes over time**  
- Provides a more credible estimate than simple OLS  

---

### 3. Two-Way Fixed Effects Model

- Controls for:
  - **State fixed effects** (permanent differences across states)  
  - **Year fixed effects** (nationwide shocks affecting all states)  

- Captures:
  - Within-state variation  
  - Common time trends  

 This is the most robust specification in the analysis  

---

## Robustness Checks

The analysis compares results across models:

- OLS vs State Fixed Effects vs Two-Way Fixed Effects  
- Evaluates how estimates change when controlling for additional factors  

This helps identify whether results are driven by bias or reflect a stable relationship  

---

## Key Findings

- The simple OLS model suggests a **positive relationship**, which is likely biased  
- After controlling for state differences, the effect becomes **negative**  
- Two-way fixed effects confirm that higher beer taxes are associated with **lower traffic fatalities**  

 The change in results highlights the importance of controlling for unobserved factors  

- Most variation in fatality rates is explained by **state-level characteristics**, not beer taxes alone  
- The within-state explanatory power of beer taxes is relatively modest  

---

## Causal Interpretation

For the results to be interpreted causally, several assumptions must hold:

- **Parallel trends:** In the absence of policy changes, states would follow similar trends over time  
- **No time-varying confounders:** No other simultaneous policy changes affecting both taxes and fatalities  
- **No reverse causality:** Policy changes are not driven by changes in fatality rates  

 Violations of these assumptions may bias the estimates  and for some of them like reverse causality we can apply models 
 like system GMM or System Generalized Method of Moments (Arellano-Bond Model). But again this method can not fix the problem like time- varying confounders. 

---

## Business / Policy Insight

- Simple correlations can be misleading when analyzing policy impacts  
- Controlling for hidden differences is critical for credible conclusions  
- Fixed effects models provide a powerful framework for evaluating real-world interventions  

This approach is widely applicable to:
- Pricing strategies  
- Policy evaluation  
- Longitudinal business data
- Digital market reviews (used in other project named **Hotel Review Panel Analysis**)

---

## Skills Demonstrated

- Panel data analysis  
- Fixed effects modeling (one-way and two-way)  
- Causal inference  
- Omitted variable bias analysis  
- Model comparison and interpretation  
- Translating econometric results into practical insights  
