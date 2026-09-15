# Network Effects and Experimental Design

## Project Overview

This project compares different experimental designs for estimating treatment effects when **network effects or spillovers** may exist.

The setting is a hypothetical Zynga mobile game where a new multiplayer feature is introduced across **36 cities and 36,000 users**. The main business question is:

> **How much does the multiplayer feature increase user revenue, especially if the value of treatment depends on how many other users are treated?**

---

## Main Goals

The project focuses on:

* estimating treatment effects under different randomization strategies,
* understanding the **bias–variance tradeoff**,
* measuring the impact of **network interference**,
* separating **direct effects** from **indirect/spillover effects**,
* understanding how treatment effects change with **treatment saturation**,
* estimating the likely effect of a **full-market rollout**.

---

## Experimental Designs

Three designs are compared:

### Person-Level Randomization

Users are individually randomized to treatment or control.

This design provides high statistical precision, but when spillovers exist, treated and control users within the same city may affect each other.

### City-Level Randomization

Entire cities are assigned to treatment or control.

This reduces interference between treatment and control groups, but statistical precision is lower because there are only 36 independent randomized cities.

### Two-Stage Randomization

Cities are first assigned different treatment saturation levels, and users are then randomized within each city.

This design allows us to estimate how the treatment effect changes as more users in the same network receive treatment.

---

## Methods

The analysis uses:

* Difference in average revenue between treatment and control groups
* Bootstrap standard errors
* Cluster-level bootstrap for city-randomized experiments
* Within-city treatment effect estimation
* Treatment saturation measurement
* Linear regression of treatment effects on saturation

For the two-stage experiment, the main model is:

$$
\hat{\tau}(p)=\alpha+\beta p
$$

where:

* \(\alpha\) represents the estimated **direct effect**
* \(\beta\) represents the additional **network/spillover effect**
* \(p\) is the proportion of users treated in a city

---

## Key Statistical Ideas

The project highlights an important tradeoff:

* **Person-level randomization:** low variance but potentially affected by interference
* **City-level randomization:** less interference but much higher variance
* **Two-stage randomization:** intermediate precision while explicitly modeling network effects

The two-stage approach is particularly useful because a standard individual-level experiment may only estimate the effect at the experiment's current treatment saturation, not necessarily the effect of treating the entire market.

The analysis assumes a constant direct effect, additive direct and indirect effects, and a linear relationship between saturation and treatment effect. Real network effects may be nonlinear because of congestion, thresholds, capacity constraints, behavioral responses, or other market effects.

---

## Main Results and Implications

The main estimates were:

| Design / Effect                  | Estimate | Bootstrap SE |
| -------------------------------- | -------: | -----------: |
| Person-level treatment effect    |    $3.81 |        $0.15 |
| City-level treatment effect      |    $2.02 |        $3.40 |
| Two-stage direct effect          |    $2.22 |        $0.49 |
| Two-stage indirect effect        |    $2.70 |        $0.88 |
| Estimated full-saturation effect |    $4.92 |        $0.45 |

The results show that the person-level experiment is very precise, while the city-level experiment is much noisier. The two-stage design provides a useful middle ground by maintaining reasonable precision while also identifying network effects.

The most important business implication is that the treatment effect can change as adoption increases. Therefore, the effect observed in a partially treated market may not equal the effect of a full rollout.

## Key Takeaway

When network effects are present, the choice of experimental design determines not only the precision of the estimate, but also **which treatment effect is being estimated**.

Two-stage randomization is especially valuable when the goal is to understand both the direct impact of treatment and how that impact changes as more users in the network are treated(Indirect or Spillover effect)
