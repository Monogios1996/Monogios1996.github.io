---
title: "Activity 01 — Correlation and Regression"
permalink: /modules/machine-learning/activities/unit-03-correlation-regression/
description: Four executed notebooks investigating noise, outliers, regression and model complexity.
---

# Activity 01 — Correlation and regression

**Module:** Machine Learning · **Unit:** 3 · **Recorded:** 5 November 2026 · **Evidence ID:** ML-01

[Machine Learning overview]({{ '/modules/machine-learning/' | relative_url }}) · [Artefact register]({{ '/modules/machine-learning/artefacts/' | relative_url }})

## Purpose and approach

The activity investigates how changes to data points affect covariance, Pearson correlation and regression. Four University of Essex Online teaching notebooks provide the starting point. Each corrected example is followed by controlled experiments, plots, comparison tables and interpretation. Random seeds are fixed, and the experiments change one factor at a time where possible.

The evidence includes 19 successfully executed code cells and eight figures containing the original plots and experiment panels. Cells were executed in fresh local IPython sessions; this is not a record of execution in a personal Colab account. The downloadable notebooks retain the actual outputs and can be rerun in Jupyter or Colab.

## Notebooks and supporting evidence

| Notebook | Main experiment | Download | Run in Colab |
|---|---|---|---|
| 1. Covariance and Pearson correlation | Noise, sign, scale and a nonlinear relationship | [Notebook]({{ '/modules/machine-learning/evidence/unit-03/Unit03_Ex1_Correlation.ipynb' | relative_url }}) | [Open](https://colab.research.google.com/github/Monogios1996/Monogios1996.github.io/blob/main/modules/machine-learning/evidence/unit-03/Unit03_Ex1_Correlation.ipynb) |
| 2. Simple linear regression | Offset, an influential observation and noise | [Notebook]({{ '/modules/machine-learning/evidence/unit-03/Unit03_Ex2_Linear_Regression.ipynb' | relative_url }}) | [Open](https://colab.research.google.com/github/Monogios1996/Monogios1996.github.io/blob/main/modules/machine-learning/evidence/unit-03/Unit03_Ex2_Linear_Regression.ipynb) |
| 3. Multiple linear regression | Predictor changes, target perturbation and held-out evaluation | [Notebook]({{ '/modules/machine-learning/evidence/unit-03/Unit03_Ex3_Multiple_Regression.ipynb' | relative_url }}) | [Open](https://colab.research.google.com/github/Monogios1996/Monogios1996.github.io/blob/main/modules/machine-learning/evidence/unit-03/Unit03_Ex3_Multiple_Regression.ipynb) |
| 4. Polynomial regression | Polynomial degree, noise, an altered observation and extrapolation | [Notebook]({{ '/modules/machine-learning/evidence/unit-03/Unit03_Ex4_Polynomial_Regression.ipynb' | relative_url }}) | [Open](https://colab.research.google.com/github/Monogios1996/Monogios1996.github.io/blob/main/modules/machine-learning/evidence/unit-03/Unit03_Ex4_Polynomial_Regression.ipynb) |

**Supporting files:** [Numerical results (JSON)]({{ '/modules/machine-learning/evidence/unit-03/results.json' | relative_url }}) · [Teaching dataset (CSV)]({{ '/modules/machine-learning/evidence/unit-03/cars.csv' | relative_url }}) · [Execution environment]({{ '/modules/machine-learning/evidence/unit-03/environment_versions.json' | relative_url }}) · [Dependencies]({{ '/modules/machine-learning/evidence/unit-03/requirements.txt' | relative_url }})

To rerun an experiment, open its notebook, run all cells, find **Change these values**, change one parameter and run all cells again. Exercise 3 embeds its data, so it requires no separate CSV upload.

## Results and critical interpretation

### Covariance and correlation

Increasing independent noise reduced Pearson r from **0.8876 to 0.3737**. Reversing the signal produced **−0.8832**. Multiplying y by ten multiplied covariance by ten but left correlation unchanged. For the symmetric relationship y = x², Pearson r was approximately zero despite an exact nonlinear relationship. Pearson correlation therefore describes linear association, not every form of dependence (SciPy developers, n.d.).

<figure>
  <img src="{{ '/modules/machine-learning/evidence/unit-03/correlation-comparison.png' | relative_url }}" alt="Five scatterplots comparing the baseline correlation with increased noise, a negative relationship, rescaled y and a symmetric squared relationship." style="max-width:100%;height:auto;">
  <figcaption>Figure 1. Controlled correlation experiments using fixed random draws.</figcaption>
</figure>

The finite-sample covariance increased slightly in the noisier condition, even though r decreased. This is a useful warning against treating unstandardised covariance as a direct measure of association strength across different variances.

### Simple linear regression

The original fitted equation was **y = 103.1060 − 1.7513x**, with training **R² = 0.5755**. Adding 20 to every y value changed the intercept and predictions without changing the slope or R². Changing only the observation at x = 17 from y = 86 to y = 160 reversed the slope to **+1.5703** and reduced R² to **0.0919**. An influential observation can therefore change the apparent direction of a fitted relationship. Its validity must be investigated before deciding whether to retain or remove it.

### Multiple linear regression

The fitted weight and engine-volume coefficients were **0.00755095** and **0.00780526**, respectively. Increasing one training CO₂ value by 100 g/km changed the weight coefficient to **0.03814672** and changed the prediction for a 1400 kg, 1600 cm³ car from **102.7545 to 108.9059 g/km**.

On the same nine held-out cars, the volume-only model had RMSE **7.1557 g/km**, compared with **7.1902 g/km** for weight plus volume. Adding a predictor did not improve that particular held-out result. The sample is too small to establish a generally superior model. Coefficients describe fitted associations while holding the other predictor fixed; they are not causal emissions effects. The original 2300 kg and 3300 kg predictions extrapolate beyond the observed weight range of **790–1746 kg**.

### Polynomial regression

The original cubic fitted to all 18 observations achieved training **R² = 0.9432** and predicted **88.8733** at 17:00. Noise reduced training R² to **0.7965**, while changing one observation reduced it to **0.3299**.

The separate degree comparison used 14 training observations and four fixed, interior held-out points:

| Degree | Training R² | Held-out RMSE | Extrapolated prediction at x = 25 |
|---|---:|---:|---:|
| 1 | 0.1761 | 9.7257 | 92.4358 |
| 2 | 0.7567 | 5.3478 | 133.9280 |
| 3 | 0.9405 | 2.2726 | 91.2145 |
| 10 | 0.9921 | 1.9514 | 1831.6390 |

<figure>
  <img src="{{ '/modules/machine-learning/evidence/unit-03/polynomial-comparison.png' | relative_url }}" alt="Polynomial curves of degrees one, two, three and ten, with training observations and four held-out interior observations marked separately." style="max-width:100%;height:auto;">
  <figcaption>Figure 2. Polynomial degree comparison on the same train and evaluation split.</figcaption>
</figure>

Degree 10 performed slightly better on the four held-out points, so it would be inaccurate to claim that higher complexity necessarily worsened test performance. Its extreme extrapolation instead demonstrates instability outside the observed range. This split evaluates interpolation, not a genuine next-day forecast. R² can be negative and a high training R² alone does not demonstrate predictive validity (Scikit-learn developers, n.d.).

## Reflection and professional implications

The central lesson is that a numerical score must be interpreted in the context of the data and evaluation design. A high correlation can weaken when noise increases, one observation can reverse a fitted slope, and a flexible model can perform well on a few interior evaluation points while extrapolating implausibly. These findings support checking plots, residual behaviour, data coverage and held-out errors together.

The multiple-regression example also separates two operations that are easy to confuse: changing an input for prediction leaves the trained model unchanged, whereas changing a training observation and refitting changes the estimated relationship. Fixed seeds and clearly labelled scenarios make these differences reproducible.

For professional use, unusual observations should be investigated rather than removed to obtain a better score. Small teaching datasets do not establish representativeness across populations or operating conditions. Data provenance, appropriate permissions, privacy safeguards and honest communication of uncertainty would need explicit consideration in any real application. The automotive example must not be presented as regulatory emissions evidence. This activity supports analysis of these responsibilities; it does not demonstrate legal compliance or deployment readiness.

## Corrections, attribution and limitations

- **Exercise 2:** corrected `stat` to `stats` and plotted the fitted line in sorted x order.
- **Exercise 3:** the missing CSV was replaced with the matching W3Schools demonstration dataset. It reproduces the coefficients and predictions shown in the supplied example. Units are g/km; the data are for teaching and testing (W3Schools, n.d.).
- **Exercise 4:** corrected the R² explanation and distinguished interpolation from forecasting.
- **Attribution:** original exercises were supplied by University of Essex Online. Corrections, extended experiments and explanatory material were prepared with AI assistance; the saved outputs are from actual Python execution. This entry does not claim that the original teaching code was independently authored.
- **Evidence limits:** the small held-out sets support illustration, not robust model selection. The saved evidence does not include tutor feedback or a personal Colab rerun.

## Development actions

1. Repeat the controlled comparisons with a second seed and record how stable the conclusions are.
2. Add residual plots and repeated validation before selecting a model for a larger dataset.
3. Use a time-aware evaluation and multiple days of observations for any genuine traffic-forecasting task.
4. Record the source, units, intended population and limitations of each future dataset before fitting a model.

[Learning-outcome mapping]({{ '/modules/machine-learning/learning-outcomes/' | relative_url }}) · [Skills and development]({{ '/modules/machine-learning/skills-development/' | relative_url }})

## References

University of Essex Online (2026) *Unit 3 practical activity: covariance, correlation and regression* [four teaching notebooks supplied with the module activity].

SciPy developers (n.d.) *pearsonr*. Available at: [https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html) (Accessed: 5 November 2026).

Scikit-learn developers (n.d.) *r2_score*. Available at: [https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html) (Accessed: 5 November 2026).

W3Schools (n.d.) *Python machine learning: multiple regression*. Available at: [https://www.w3schools.com/python/python_ml_multiple_regression.asp](https://www.w3schools.com/python/python_ml_multiple_regression.asp) (Accessed: 5 November 2026).
