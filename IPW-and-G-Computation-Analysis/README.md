# Causal Inference in Health Policy: IPW and G-Computation Analysis

## Overview

This project evaluates whether mosquito nets reduce malaria risk and quantifies the magnitude of their impact using causal inference methods.

The goal is to move beyond simple correlations and estimate **causal effects** by addressing selection bias and constructing counterfactual outcomes.

The analysis compares multiple approaches to understand how different methods estimate treatment effects under non-random treatment assignment.

---

## Methodology

The dataset contains household-level information including:

- Mosquito net usage (treatment)  
- Malaria risk (outcome)  
- Socioeconomic and environmental characteristics (covariates)  

### Key Challenge

Households that use mosquito nets are systematically different from those that do not (like income, health awareness, environment).

 This creates **selection bias**, making simple comparisons misleading.

---

## Estimation Approaches

### 1. Ordinary Least Squares (OLS)

- Estimates the association between net usage and malaria risk  
- Shows a large reduction in malaria risk  
- Does not control for differences between treated and untreated groups  

 Likely **overestimates the true effect** due to confounding  

---

### 2. Inverse Probability Weighting (IPW)

- Reweights observations based on probability of receiving treatment  
- Creates a balanced comparison between treated and control groups  
- Approximates a randomized experiment  

 Provides a more reliable estimate of the **Average Treatment Effect (ATE)**  

---

### 3. G-Computation (ATT Estimation)

- Models the outcome for the control group  
- Predicts what treated households’ outcomes would have been without treatment  
- Compares observed outcomes to counterfactual predictions  

 Estimates the **Average Treatment Effect on the Treated (ATT)**  

---

## Heterogeneity Analysis

The project highlights differences between treatment effect measures:

- **ATE** → effect across the entire population  
- **ATT** → effect for those who actually received treatment  
- **ATU** → effect for those who did not receive treatment  

 These measures answer different policy questions and may produce different estimates  

---

## Robustness Checks

- Comparison across OLS, IPW, and G-computation  
- Bootstrap simulation (1,000 repetitions) to assess variability  
- Confidence interval estimation for ATT  

 Bootstrap results show stable estimates and provide uncertainty bounds  

---

## Key Findings

- OLS estimates show a large reduction in malaria risk (~ -16), likely biased  
- IPW estimates a smaller but still significant effect (~ -12), correcting for selection bias  
- G-computation (ATT) shows a more targeted effect (~ -8.8) for treated households  
- Bootstrap results confirm that ATT estimates are stable and statistically meaningful  

 The difference across methods highlights the importance of adjusting for confounding  

---

## Business / Policy Insight

- Simple comparisons can **overstate intervention effectiveness**  
- Causal methods provide more realistic estimates for decision-making  
- The choice of treatment effect depends on the policy goal:
  - **ATE** → scaling intervention to entire population  
  - **ATT** → evaluating existing programs  
  - **ATU** → targeting untreated populations  

 Understanding these differences is critical for effective policy design  

---

## Skills Demonstrated

- Causal inference (ATE, ATT, ATU)  
- Inverse Probability Weighting (IPW)  
- G-computation  
- Counterfactual reasoning  
- Bootstrap inference and uncertainty estimation  
- Translating statistical results into policy insights
    
