# Synthetic Control Analysis: Impact of California Smoking Ban on Cigarette Sales

## Overview

This project replicates the research that evaluated the causal impact of California’s 1988 tobacco control program on cigarette sales using the Synthetic Control Method.

The goal is to estimate what cigarette consumption in California would have looked like **in the absence of the policy**, and compare it to the observed outcome after the intervention.

Since we cannot directly observe this counterfactual, a synthetic version of California is constructed using a weighted combination of other U.S. states.

---

## Methodology

The analysis uses panel data of U.S. states over time.

### Key Elements:
- **Treated unit:** California  
- **Intervention year:** 1988  
- **Outcome:** Cigarette sales  
- **Control group:** Other U.S. states  

A synthetic control is constructed to closely match California’s behavior before the policy using predictors such as:

- Income  
- Cigarette prices  
- Beer consumption  
- Youth population share  

---

## Estimation Approaches

### 1. Synthetic Control (Synth Package)

- Constructs a weighted combination of control states  
- Matches California’s pre-treatment trajectory  
- Provides a transparent counterfactual  

---

### 2. Synthetic Control (Tidysynth)

- Implements the same methodology using a tidyverse-friendly framework  
- Simplifies data manipulation and visualization  
- Confirms robustness of results across implementations  

---


## Robustness Checks

- Comparison between Synth and Tidysynth implementations  
- Evaluation of pre-treatment fit  
- Visual inspection of trends and gaps  

A strong pre-treatment fit increases confidence in the validity of the counterfactual  

---

## Key Findings

- Before 1988, synthetic California closely tracks actual California  
- After the policy, cigarette sales in California decline significantly relative to the synthetic control  
- The estimated average treatment effect is **negative (approximately -20 units)**  

 This indicates that the smoking ban had a substantial impact in reducing cigarette consumption  

---

## Business / Policy Insight

- Policy interventions can have measurable and significant behavioral effects  
- Synthetic control provides a powerful framework when randomized experiments are not feasible  
- Constructing a credible counterfactual is essential for causal inference  

This method is highly applicable to:

- Policy evaluation  
- Market interventions  
- Strategic business decisions
  
Especially we have not direct access to actual control group to use the control group as is like DiD. So we have to re-weights and combines control groips to build a better match for tretament group. 

---

## Skills Demonstrated

- Synthetic Control Method  
- Causal inference and counterfactual analysis  
- Panel data analysis  
- Policy evaluation  
- Data visualization and interpretation  
- Translating empirical results into actionable insights  
