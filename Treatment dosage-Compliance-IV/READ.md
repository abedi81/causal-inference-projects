# Advertising Intensity and User Engagement: A Pandora-Style Experiment

## Overview

This project analyzes the causal impact of advertising intensity on user engagement in a music streaming platform using a dataset structured similarly to the Pandora ad-load experiment. The main goal of the project is to understand how increasing advertisement exposure affects users’ listening behavior and how this effect changes over time and across demographic groups.

The analysis goes beyond a simple treatment-versus-control comparison and focuses on four major concepts:

- Treatment dosage effects
- Dynamic treatment effects over time
- Non-compliance and instrumental variables (IV)
- Heterogeneous treatment effects across age groups

---

## Main Analysis

### 1. Treatment Dosage Effects

The project first examined how different levels of intended ad exposure affected listening time at the end of the experiment. Results showed that higher advertising intensity reduced user engagement, especially in high-ad-load treatment groups.

A continuous treatment regression estimated that:

> Increasing intended ad exposure by one additional ad-minute per hour reduced weekly listening time by approximately 6.3 minutes.

---

### 2. Dynamic Treatment Effects

Using the full panel dataset across all weeks, the project studied how treatment effects evolved over time.

The analysis showed that:

- the negative effect of ads was relatively small at the beginning,
- but gradually became stronger over time,
- eventually stabilizing around **-6 to -7 minutes**.

This suggests the existence of cumulative ad fatigue, where users become increasingly sensitive to advertising exposure over time.

---

### 3. Non-Compliance and Instrumental Variables

A key challenge in the experiment was that actual ad exposure did not perfectly match assigned ad exposure because of user behavior and platform delivery dynamics.

To address this endogeneity problem, the project implemented an instrumental variable (IV) framework using intended ad load as an instrument for actual ad exposure.

The IV analysis showed that:

> Increasing actual ad exposure by one additional ad-minute per hour causally reduced weekly listening time by approximately 7.6 minutes.

The IV estimate was more negative than the reduced-form estimate, indicating that imperfect treatment realization diluted the naive treatment effect.

---

### 4. Heterogeneous Treatment Effects

The project also examined whether different age groups responded differently to advertising intensity.

The strongest negative effect was observed among users aged **25–54**, who showed both:

- the largest decline in listening time from increased ads,
- and the largest difference between reduced-form and IV estimates.

This suggests that middle-aged users were the most sensitive to advertising intensity and were most affected by non-compliance dynamics.

---

## Key Findings

- Higher ad exposure reduces user engagement.
- The negative impact of ads becomes stronger over time.
- Actual ad exposure differs from intended ad exposure, creating a non-compliance problem.
- Instrumental variables help isolate the causal effect of actual ads.
- Users aged 25–54 are the most sensitive demographic group to increased advertising intensity.

---

## Methods and Tools

This project combines several econometric and experimental methods, including:

- Difference in means and t-tests
- Panel data analysis
- Dynamic treatment effect estimation
- Instrumental variables (IV)
- Two-stage least squares (2SLS)
- Interaction models for heterogeneous effects

Libraries used:

- pandas
- matplotlib
- scipy
- statsmodels

---

## Conclusion

This project demonstrates how experimental and panel data methods can be used to estimate the causal effect of advertising intensity on user behavior in digital platforms. By combining dosage analysis, dynamic effects, instrumental variables, and subgroup analysis, the project provides a comprehensive understanding of how users respond to advertising over time.


### Visulization 

#### Treatment Effect Over Time

The figure below shows how the negative effect of ad load evolves across weeks of the experiment.

 <img width="452" height="232" alt="Screenshot 2026-05-20 183954" src="https://github.com/user-attachments/assets/bc32d8ae-552e-464f-ba1e-22c223724f98" />


---

#### T-Statistics Over Time

The following figure shows when the treatment effect became statistically significant.

<img width="448" height="234" alt="Screenshot 2026-05-20 184014" src="https://github.com/user-attachments/assets/fc58db82-27a8-412d-ac78-5c73868cc748" />


---

#### Intended vs Actual Ad Exposure

This scatter plot illustrates imperfect treatment realization and non-compliance.

<img width="397" height="352" alt="Screenshot 2026-05-20 191553" src="https://github.com/user-attachments/assets/feb8d773-da01-4d54-a0c2-464772a45b7a" />

