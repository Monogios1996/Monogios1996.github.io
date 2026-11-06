---
title: Machine Learning — Learning Log
permalink: /modules/machine-learning/learning-log/
---

# Machine Learning — Learning log

[Module overview]({{ '/modules/machine-learning/' | relative_url }})

## 5 November 2026 · Unit 3 practical activity

**Evidence:** [ML-01 — Correlation and regression]({{ '/modules/machine-learning/activities/unit-03-correlation-regression/' | relative_url }})

### Work recorded

Four teaching notebooks were corrected, extended and executed. The experiments varied noise, measurement scale, individual observations, predictors and polynomial degree. The saved evidence contains comparison tables, plotted results and an account of the execution method.

### Findings

- Pearson r fell from 0.8876 to 0.3737 when noise increased; rescaling y changed covariance but not r.
- A symmetric squared relationship produced r close to zero, demonstrating the limits of a linear association measure.
- Changing one observation reversed the simple-regression slope from −1.7513 to +1.5703.
- Adding weight to engine volume did not improve held-out RMSE in the small automotive split.
- A degree-10 polynomial slightly improved held-out interpolation error but extrapolated implausibly at x = 25.

### Interpretation

The results support evaluating the relationship between a model and its dataset rather than treating a high score as sufficient evidence. Coefficients, training fit, held-out performance and extrapolation answer different questions. Small datasets and a single split limit the strength of any conclusion.

### Next steps

Repeat the experiments with a second seed, add residual plots, and compare repeated validation results. A future forecasting exercise should use a chronological split and observations across multiple days. These are development actions, not experiments claimed as completed in this entry.

[Skills and development]({{ '/modules/machine-learning/skills-development/' | relative_url }})
