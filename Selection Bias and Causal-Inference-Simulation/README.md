# Causal Inference in A/B Testing: Simulation Study

## Overview

This project builds a simulated dataset to demonstrate core concepts in causal inference and A/B testing.

The objective is to show:
- How **selection bias** arises under non-random treatment assignment  
- Why naive comparisons between treated and control groups are misleading  
- How **randomized experiments (A/B tests)** recover the true causal effect  

The analysis is conducted from the perspective of an **“omniscient observer”**, where both potential outcomes are known, allowing validation of estimated effects against the true treatment effect.

---

## Methodology

We simulate data for **1,000 consumers** with the following variables:

- `consumer_ID` → unique identifier  
- `distance` → distance from the restaurant  
- `past_spend` → previous spending behavior  

### Non-Random Treatment Assignment

Consumers are exposed to ads (`see_ad = 1`) if:
- Distance ≤ 10 miles  
- Past spending > $50  

 This creates **selection bias**, since treated consumers are inherently different from control consumers.

---

## Estimation Approaches

The project compares three approaches:

### 1. True Treatment Effect (Benchmark)
### 2.Naive Difference (Biased Estimate)
### 3. Experimental A/B Testing (Unbiased Estimate)


--- 

### Heterogeneity Analysis

The treatment effect is not uniform across consumers:

## Consumers within 10 miles
Higher responsiveness
Expected increase ≈ +$20
## Consumers beyond 10 miles
Lower responsiveness
Expected increase ≈ +$10

---

## Simulation Validation

To evaluate reliability:

- The experiment is repeated multiple times
- ATE estimates vary due to random sampling variation
- The average estimated ATE converges to the true effect

---

### Key Findings

- Non-random ad exposure leads to selection bias
- Naive comparisons overestimate treatment effects
- Randomized experiments recover the true causal effect
- Treatment effects vary significantly across consumer segments
- Repeated experiments confirm the consistency of A/B testing estimates

---

### Business Insight

- Targeting ads based on user characteristics can introduce biased performance estimates
- Reliable measurement of ad effectiveness requires randomized experimentation
- Consumer proximity (or similar features) can strongly influence responsiveness
- Understanding who responds to ads is as important as measuring overall impact

---


### Skills Demonstrated

- Causal inference fundamentals
- Potential outcomes framework
- Selection bias and endogeneity
- A/B testing and experimental design
- Simulation-based analysis
- Treatment effect interpretation (ATE, heterogeneity)
