# Treatment Effect Estimation: OLS vs AIPW vs Causal Forest (Simulation Study)

## Overview

This project simulates a causal inference experiment to evaluate how different estimation methods recover the true treatment effect under varying data-generating processes (DGPs).

The objective is to compare:
- **Parametric models (OLS)**  
- **Semi-parametric methods (AIPW)**  
- **Nonparametric machine learning methods (Causal Forests)**  

and understand how they perform under **linear vs nonlinear environments** and across different sample sizes.

---

## Methodology

We simulate data where:

- Covariates (`X1, X2, X3`) are randomly generated  
- Treatment assignment (`W`) depends on covariates  
- Outcome (`Y`) is generated using:
  - A **linear DGP**
  - A **nonlinear DGP**

The true treatment effect (τ) is known, allowing direct evaluation of estimator performance.

Monte Carlo simulations are used to:
- Repeatedly sample data  
- Estimate treatment effects  
- Analyze estimator bias and variability  

---

## Estimation Approaches

### 1. Ordinary Least Squares (OLS)

- Assumes a **linear relationship** between variables  
- Efficient when the model is correctly specified  
- Sensitive to model misspecification  

---

### 2. Augmented Inverse Probability Weighting (AIPW)

- Combines:
  - Outcome modeling  
  - Propensity score weighting  
- Doubly robust:
  - Consistent if either model is correctly specified  
- Implemented using **random forests** for flexibility  

---

### 3. Causal Forest

- Fully nonparametric machine learning method  
- Learns treatment effects directly from data  
- Captures:
  - Nonlinear relationships  
  - Treatment effect heterogeneity  

---

## Heterogeneity Analysis

Causal Forests enable analysis beyond average effects by identifying:

- Variation in treatment effects across individuals  
- Subgroup-level differences  
- Complex interactions between covariates  

This reflects real-world settings where treatment effects are rarely uniform.

---

## Robustness Checks

The project evaluates estimator performance across:

- **Different sample sizes**  
- **Linear vs nonlinear data-generating processes**  
- **Repeated Monte Carlo simulations**  

This allows assessment of:
- Bias  
- Variance  
- Consistency  

---

## Key Findings

- **OLS performs best in linear settings**
  - Recovers the true effect efficiently  
  - Variance decreases with larger sample sizes  

- **OLS fails under nonlinear DGP**
  - Converges to incorrect estimates  
  - Produces misleading confidence due to model misspecification  

- **AIPW provides robustness**
  - Performs well in both linear and nonlinear settings  
  - Less efficient in small samples but improves with more data  

- **Causal Forest is the most flexible**
  - Recovers treatment effects in complex environments  
  - Captures heterogeneity across individuals  
  - Requires larger sample sizes to stabilize  

---

## Business Insight

- Simple models (like linear regression) can be **misleading** when relationships are complex  
- Flexible methods (AIPW, causal ML) are more reliable in real-world settings  
- There is a trade-off between:
  - **Efficiency (simple models)**  
  - **Robustness (machine learning models)**  

Choosing the wrong model can lead to **incorrect business decisions**, even with large datasets  

---

## Skills Demonstrated

- Causal inference and treatment effect estimation  
- Monte Carlo simulation  
- Model evaluation under misspecification  
- Doubly robust estimation (AIPW)  
- Causal machine learning (Causal Forest)  
- Bias-variance trade-off analysis  
- Translating statistical concepts into practical insights  
