# YouTube Treatment Effect Shrinkage Analysis

## Project Overview

This project investigates whether **shrinkage and regularization methods can improve treatment-effect estimates** across multiple randomized experiments.

YouTube conducted **50 separate week-long experiments** designed to measure whether different treatments increased users' time spent on the platform.

Each experiment contains:

- 1,000 treatment users
- 1,000 control users
- 2,000 users total

Across all 50 experiments, the dataset contains **100,000 user-level observations**.

For each user, the outcome is the change in weekly time spent on YouTube relative to the previous week.

The main question is:

> Can we obtain more accurate treatment-effect estimates by borrowing information across experiments instead of estimating every experiment completely independently?

---

## Data

### Experimental Data

The main dataset contains three variables:

| Variable | Description |
|---|---|
| `outcome` | Change in weekly time spent on YouTube |
| `treatment` | 1 = treatment, 0 = control |
| `experiment_number` | Experiment ID from 1 to 50 |

For each experiment, the treatment effect is estimated as:

`beta_hat_j = mean(Y_treatment) - mean(Y_control)`

Since treatment is binary, this is also exactly the treatment coefficient from the regression:

`Y = alpha + beta * Treatment + error`

---

### True Treatment Effects

A second dataset contains the true treatment effect for each of the 50 experiments.

These values are **not used to construct any treatment-effect estimates**.

They are used only afterward to evaluate estimation accuracy using Mean Squared Error:

`MSE = average[(estimated effect - true effect)^2]`

This separation is important because the purpose of the project is to estimate effects using only information that would actually be available to the analyst.

---

## Methodology

I compare five approaches for estimating the 50 treatment effects:

1. Frequentist estimation
2. James-Stein shrinkage
3. Split-sample shrinkage
4. LASSO
5. Ridge regression

---

## 1. Frequentist Baseline

I first estimate each experiment independently using OLS:

`Y = alpha + beta * Treatment + error`

Because treatment is binary:

`beta_hat = mean(Y_treatment) - mean(Y_control)`

This produces 50 independent treatment-effect estimates.

The resulting treatment-effect MSE is:

**Frequentist MSE = 1.061**

This serves as the baseline for evaluating the shrinkage methods.

---

## 2. James-Stein Shrinkage

James-Stein shrinkage takes the 50 ordinary treatment-effect estimates and shrinks them toward zero.

The estimator is:

`beta_JS = delta * beta_hat`

The common sampling variance estimated from the experiments was:

**Estimated variance = 0.799**

The resulting shrinkage factor was:

**delta = 0.731**

This means each original estimate was multiplied by approximately 0.731.

The final result was:

**James-Stein MSE = 0.625**

This represents a substantial improvement over the frequentist baseline.

Importantly, the true treatment effects were **not used to calculate the shrinkage factor**. They were used only afterward to calculate MSE.

---

## 3. Split-Sample Shrinkage

For this approach, I divided each experiment into two independent halves.

Each half contained approximately:

- 500 treatment users
- 500 control users

I estimated the treatment effect separately in each half and then regressed the second-half estimates on the first-half estimates:

`beta_B = a + b * beta_A + error`

The estimated parameters were:

**Intercept = 0.205**

**Shrinkage slope = 0.653**

I then applied this learned relationship to the full-sample treatment effects:

`beta_split = 0.205 + 0.653 * beta_full`

The final result was:

**Split-Sample MSE = 0.630**

This method performed almost as well as James-Stein while learning the amount of shrinkage directly from the experimental data.

---

## 4. LASSO

LASSO shrinks the treatment coefficient using an L1 penalty.

Conceptually, it minimizes:

`Prediction Error + alpha * |treatment coefficient|`

Larger values of `alpha` produce stronger shrinkage and can eventually force the treatment coefficient to zero.

I tested the following candidate values:

`[0.001, 0.005, 0.01, 0.05, 0.1, 0.5, 1, 5, 10, 50, 100, 500, 1000]`

I selected `alpha` using **2-fold cross-validation** based on prediction error.

The best value was:

**Best alpha = 0.5**

with:

**Cross-validation prediction MSE = 400.348**

After refitting LASSO on the full data for each experiment:

**LASSO treatment-effect MSE = 0.888**

LASSO improved on the frequentist baseline, although it did not perform as well as James-Stein or split-sample shrinkage.

---

## 5. Ridge Regression

Ridge regression uses an L2 penalty that smoothly shrinks the treatment coefficient toward zero.

Conceptually, it minimizes:

`Prediction Error + alpha * (treatment coefficient)^2`

The same set of candidate `alpha` values was evaluated using 2-fold cross-validation.

The selected value was:

**Best alpha = 100**

with:

**Cross-validation prediction MSE = 400.326**

After refitting Ridge using the full data:

**Ridge treatment-effect MSE = 0.742**

Ridge therefore improved substantially over the frequentist baseline and performed better than LASSO.

---

## Results

| Method | Treatment-Effect MSE |
|---|---:|
| Frequentist | 1.061 |
| James-Stein | **0.625** |
| Split-Sample Shrinkage | 0.630 |
| Ridge | 0.742 |
| LASSO | 0.888 |

All four shrinkage or regularization approaches produced lower treatment-effect MSE than the standard frequentist estimator.

Among the individual methods, **James-Stein achieved the lowest MSE**, followed very closely by the split-sample approach.

---

## Combined Shrinkage Estimate

I also combined the four shrinkage estimates for each experiment:

`Average Shrinkage = (James-Stein + Split-Sample + LASSO + Ridge) / 4`

For each experiment, I then calculated the estimation error.

For the frequentist estimator:

`Frequentist Error = Frequentist Estimate - True Effect`

For the combined shrinkage estimator:

`Average Shrinkage Error = Average Shrinkage Estimate - True Effect`

Unlike MSE, these errors were **not squared**, because the goal was to compare their full distributions.

---

## Error Distribution

The density plot compares:

- 50 frequentist estimation errors
- 50 average-shrinkage estimation errors

The average-shrinkage errors are more tightly concentrated around zero than the frequentist errors.

This suggests that combining the shrinkage methods produces:

- lower variability
- fewer extreme estimation errors
- more stable treatment-effect estimates

The average-shrinkage distribution is slightly shifted to the right of zero, suggesting a small tendency toward overestimation.

---

## Key Findings

- Estimating each experiment independently produces relatively noisy treatment-effect estimates.
- Shrinkage can reduce this noise by borrowing information across experiments.
- All four shrinkage methods reduced MSE relative to the frequentist baseline.
- James-Stein achieved the lowest MSE: **0.625**.
- Split-sample shrinkage performed almost identically: **0.630**.
- Ridge achieved an MSE of **0.742**.
- LASSO achieved an MSE of **0.888**.
- Averaging the four shrinkage estimators produced a narrower distribution of estimation errors than the ordinary frequentist approach.
- True treatment effects were used only for final evaluation, never for selecting tuning parameters or constructing the estimators.

---

## Conclusion

This analysis demonstrates the value of shrinkage when estimating treatment effects across many related randomized experiments.

The standard frequentist approach is simple and interpretable, but it estimates every experiment independently and therefore retains relatively high sampling variance.

Shrinkage methods trade some bias for lower variance, which can substantially reduce overall estimation error.

For this dataset, **James-Stein shrinkage produced the lowest treatment-effect MSE**, while the split-sample method achieved nearly identical performance using a shrinkage relationship learned directly from the experimental data.
