
# Treatment Effects of Matching Donation Dosages on Charitable Giving

## Project Overview

This project analyzes a randomized field experiment on charitable giving to study whether matching donation offers increase donor participation and donation amounts. The project replicates and extends the study *“Does Price Matter in Charitable Giving?”* using causal inference methods to estimate the effect of different fundraising treatments.

## Research Question

Do matching donation campaigns increase charitable giving, and do larger matching ratios or different donation suggestions lead to stronger donor responses?

## Data

The dataset includes previous donors who were randomly assigned to different fundraising treatments. Some donors received no matching offer, while others received matching offers with different ratios, maximum match amounts, and suggested donation levels.

## Methodology

The analysis includes:

- Data cleaning and preparation
- Randomization balance checks
- Difference-in-means tests
- Difference-in-proportions tests(T-test and Z-test)
- OLS regression with robust standard errors
- Average Treatment Effect (ATE) estimation
- Permutation tests
- Bootstrap confidence intervals
- Heterogeneous treatment effect analysis

## Key Findings

The results show that matching donation offers significantly increase both the probability of donating and the average donation amount. However, larger matching ratios such as 2:1 or 3:1 did not produce statistically stronger effects compared to the basic matching offer.

The analysis also shows that donor history, donation frequency, and recency are strong predictors of future giving behavior. In addition, the treatment effect was stronger in red states compared to blue states.

## Conclusion

This project demonstrates how randomized experiments and causal inference methods can be used to evaluate fundraising strategies. The main finding is that offering a donation match matters, but increasing the size of the match does not necessarily create a stronger donor response.

## Tools Used

- Python
- Pandas
- NumPy
- Statsmodels
- Scipy
- Matplotlib
- Causal Inference
- A/B Testing
- Regression Analysis
