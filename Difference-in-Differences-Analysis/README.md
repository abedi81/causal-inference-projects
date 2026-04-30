
# Minimum Wage and Employment: A Difference-in-Differences Analysis

## Overview

This project replicates a well-known causal inference study that examines the impact of a minimum wage increase on employment in the fast-food industry.

The setting provides a natural experiment where the minimum wage increased in New Jersey while remaining unchanged in Pennsylvania. This allows for a clear comparison between a treated group and a control group.

The goal is to estimate the causal effect of the policy change on employment using Difference-in-Differences (DiD) and Fixed Effects methods.

---

## Methodology

The analysis uses data from fast-food restaurants across two regions:

- **New Jersey (Treatment group)** → minimum wage increased  
- **Pennsylvania (Control group)** → no policy change  

### Time Periods:
- **Pre-treatment** → February 1992  
- **Post-treatment** → November 1992  

### Outcome:
- Employment measured as **full-time equivalent workers (FTE)**  

This setup allows us to isolate the impact of the policy change by comparing how employment evolves over time across the two groups.

---

## Estimation Approaches

### 1. Difference-in-Differences (DiD)

- Compares changes in employment over time between treatment and control groups  
- Removes baseline differences between states  
- Isolates the causal impact of the wage increase  

---

### 2. Regression-Based DiD

- Uses a regression framework to estimate the same effect  
- Captures the interaction between time and treatment status  
- Provides statistical inference and significance testing  

---

### 3. Fixed Effects Model

- Controls for unobserved differences across stores that do not change over time  
- Accounts for common time shocks affecting all stores  
- Extends DiD into a more flexible panel data framework  

---


## Robustness Checks

- Comparison across multiple estimation methods:
  - Manual DiD  
  - Regression DiD  
  - Fixed Effects model  

- Consistency of results across approaches confirms reliability  

---

## Key Findings

- The estimated treatment effect is **positive (approximately +2.75 FTE employees)**  
- Fixed Effects results are consistent with DiD estimates  
- The minimum wage increase **did not reduce employment** in this setting  

This finding challenges the traditional view that higher wages necessarily lead to job losses  

---

## Business / Policy Insight

- Labor market responses to policy changes can be more complex than standard economic theory predicts  
- Data-driven evaluation is essential before making policy conclusions  
- Similar causal frameworks can be applied to:
  - Pricing strategies  
  - Operational changes  
  - Business experiments  

---

## Skills Demonstrated

- Difference-in-Differences (DiD)  
- Fixed Effects modeling  
- Causal inference and policy evaluation  
- Panel data analysis  
- Interpreting empirical results for real-world decisions  
