# Fuzzy Regression Discontinuity: Impact of Tutoring on Student Performance

## Overview

This project evaluates the causal impact of a tutoring program on student performance using a fuzzy regression discontinuity (RD) design.

The program assigns eligibility based on an entrance exam cutoff score. However, because participation does not perfectly follow this rule, the setting becomes a **fuzzy RD**, where the cutoff affects the probability of treatment but does not fully determine it.

The goal is to estimate whether tutoring improves students’ exit exam scores and quantify the magnitude of this effect.

---

## Methodology

The dataset includes:

- Entrance exam score (running variable)  
- Tutoring participation (treatment)  
- Exit exam score (outcome)  

### Key Design Feature

- Students scoring below the cutoff are eligible for tutoring  
- In practice:
  - Some eligible students do not participate  
  - Some ineligible students receive tutoring  

This imperfect compliance creates a **fuzzy regression discontinuity setting**

---

## Estimation Approaches

### 1. Visual Regression Discontinuity Analysis

- Examines the relationship between entrance and exit exam scores  
- Identifies discontinuity in treatment probability at the cutoff  
- Confirms that treatment assignment is not perfectly determined  

---

### 2. Two-Stage Least Squares (2SLS)

- First stage: predicts tutoring participation using cutoff eligibility  
- Second stage: estimates the effect of predicted tutoring on outcomes  

 Uses the cutoff as an **instrument** for treatment  

---

### 3. Instrumental Variables (IV) Regression

- Implements the same strategy in a formal IV framework  
- Provides a consistent estimate of the causal effect  

 Both approaches estimate the **Local Average Treatment Effect (LATE)**  

---

## Heterogeneity Analysis

The estimated effect applies specifically to:

- **Compliers** : students whose tutoring participation is influenced by the cutoff  

 This means the results do not apply to all students, but to those affected by the eligibility rule  

---

## Robustness Checks

- Comparison between manual 2SLS and IV regression results  
- Restricting analysis to observations near the cutoff (local window)  
- Verification of discontinuity in treatment probability  

 Consistent results across methods strengthen causal interpretation  

---

## Key Findings

- Tutoring increases exit exam scores by approximately **9–10 points**  
- Results are statistically significant and robust across estimation methods  
- The effect is identified locally for students near the cutoff  

 This confirms a strong positive causal impact of tutoring for borderline students  

---

## Business / Policy Insight

- Even imperfect policy rules can be used to identify causal effects  
- Fuzzy RD provides a powerful framework when compliance is incomplete  
- The results suggest that tutoring programs can significantly improve outcomes for targeted students  

 This approach is useful for:
- Education policy evaluation  
- Program targeting and optimization  
- Real-world interventions with imperfect implementation  

---

## Skills Demonstrated

- Regression Discontinuity Design (RDD)  
- Fuzzy RD and compliance analysis  
- Instrumental Variables (IV) and 2SLS  
- Local Average Treatment Effect (LATE) interpretation  
- Causal inference under imperfect treatment assignment  
- Translating empirical results into policy insights  
