# Early Stopping and Multiple Hypothesis Testing in Online Experiments

## Project Overview

This simulation project studies the statistical risks of repeated hypothesis testing and early stopping in online A/B experiments. The experiment setting is based on an online travel platform such as Airbnb or Booking.com testing whether replacing Upfront Fees (control group) with Back-End Fees (treatment group) increases customer purchase probability.

The simulation assumes:

- Baseline purchase probability: 7%

- True treatment effect: +1.5 percentage points

The main goal of the project is to analyze how continuous monitoring and repeated significance testing can distort experimental results.

---

## Research Question

What happens when companies repeatedly check p-values during an experiment and stop the test immediately after obtaining statistical significance?

---

## Methodology

The project includes:

- Statistical power analysis
- Minimum sample size estimation
- Sequential experimentation simulation
- Batch-based data arrival process
- Average Treatment Effect (ATE) estimation
- Proportions z-tests
- Early stopping simulation
- Multiple hypothesis testing analysis
- Fixed-sample testing comparison

Observations arrived sequentially in batches of 500 users. After each batch, the treatment effect and p-value were recalculated.

---

## Experimental Design

### 1. Sequential Monitoring with Early Stopping

Experiments were continuously monitored and stopped immediately once a statistically significant result was observed.

The simulation repeated this process across 200 experiments to study:

- Frequency of false significance
- Stopping bias
- Inflation of treatment effects
- Distribution of first significant estimates

### 2. Fixed Final Testing

In the second approach, no interim stopping was allowed. Statistical testing was performed only once at the predetermined final sample size.

This provided a benchmark for comparing:

- Sequential testing
- Fixed-sample testing
- Reliability of estimated treatment effects

---

## Key Findings

The simulation shows that repeated interim testing can:

- Inflate statistical significance rates
- Increase false positive risk
- Exaggerate estimated treatment effects
- Create stopping bias

In contrast, fixed-sample testing preserves more reliable statistical properties and produces more stable treatment effect estimates.

The project highlights the tradeoff between:

- Faster business decision-making
- Statistical reliability and validity

---

## Tools & Methods

- Python
- Pandas
- NumPy
- Statsmodels
- Scipy
- Matplotlib

Statistical methods used:

- A/B Testing
- Power Analysis
- Multiple Hypothesis Testing
- Sequential Experimentation
- Hypothesis Testing
- Difference in Outcomes Estimation

---

## Visualization Examples


### P-Value Monitoring Across Batches

![Cumulative False Positive Rate](https://github.com/user-attachments/assets/ab36de92-c00b-4ea4-bbe8-4e942e5a631d)

