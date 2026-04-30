# A/B Test Simulation: Power, Permutation Test, and Z-Test

## Overview

This project simulates an A/B testing experiment for an online platform (e.g., Airbnb or Booking.com) to evaluate whether switching from **Upfront Fees (UF)** to **Back-End Fees (BF)** increases the probability of purchase.

The goal is to understand:
- How treatment effects are estimated in randomized experiments  
- How statistical significance is evaluated  
- How **statistical power**, **sample size**, and **effect size** influence our ability to detect real effects  

---

## Methodology

We simulate user-level data where:

- Users are randomly assigned to:
  - **Control (UF)** → current pricing system  
  - **Treatment (BF)** → new pricing system  

- Outcome:
  - `purchase = 1` (user buys)  
  - `purchase = 0` (user does not buy)  

### Key Assumptions

- Baseline conversion rate = **7%**  
- Treatment effect = **+1.5 percentage points** (≈ 8.5%)  
- Assignment is **fully randomized** → no selection bias  

---

## Estimation Approaches

### 1. Average Treatment Effect (ATE)

- Measures the difference in purchase probability between treatment and control  
- Due to randomness and finite sample size, estimates vary around the true effect  

---

### 2. Permutation Test

- Simulates the **null hypothesis (no treatment effect)** by randomly shuffling treatment labels  
- Builds a **null distribution of ATEs**  
- Compares observed ATE to this distribution  

 Interpretation:
- If observed ATE is extreme → evidence of real effect  
- If not → effect may be due to random chance  

---

### 3. Proportion Z-Test

- Uses normal approximation to test differences in conversion rates  
- Provides:
  - Test statistic  
  - p-value  

Faster analytical alternative to permutation testing  

---



## Robustness Checks

We validate results through multiple approaches:

- **Repeated simulations** → shows variability of ATE  
- **Permutation testing** → confirms behavior under null hypothesis  
- **Comparison across methods (ATE vs Z-test vs permutation)**  

---

## Key Findings

- Estimated treatment effects fluctuate due to randomness but center around the true effect  
- With sample size ≈ 1000, the experiment has **low statistical power** (~12%)  
- Many experiments fail to detect the effect even when it exists  
- Permutation test confirms that observed effects are often indistinguishable from noise  
- Z-test produces similar conclusions regarding statistical significance  

---

## Power and Experiment Design

The simulation explores how experimental design affects detection ability:

### Effect of Sample Size
- Larger samples → lower variance → higher power  
- Detection becomes more reliable as sample size increases  

### Minimum Detectable Effect (MDE)
- With fixed sample size, only **larger effects can be reliably detected**  
- Small effects (like +1.5pp) require significantly larger samples  

### Treatment-Control Split
- Statistical power is maximized at:
  - **50% treatment / 50% control**  
- Imbalanced groups reduce power  

---

## Business Insight

- Small improvements in conversion (e.g., +1.5pp) are difficult to detect without sufficient data  
- Poorly designed experiments can lead to **false conclusions**  
- Power analysis is essential before running experiments to ensure meaningful results  
- Balanced group allocation improves reliability  
- Statistical testing (Z-test / permutation) helps validate whether observed effects are real  

---

## Skills Demonstrated

- A/B testing and experimental design  
- Statistical inference and hypothesis testing  
- Permutation testing  
- Proportion Z-test  
- Statistical power and sample size analysis  
- Simulation-based reasoning  
- Translating statistical results into practical insights  
