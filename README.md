# Statistics for Data Analysis

A structured, practical study of statistics for data analysis, experimentation, and predictive modelling - with concepts, mathematical foundations, worked examples, visual explanations, and Python applications.

This repository documents a progressive learning path from statistical foundations to regression and A/B testing. The goal is not just to memorise formulas, but to understand **when a method is appropriate, what its results mean, and how to use it responsibly in real data work**.

---

## Repository roadmap

| Module | Topic | What it covers |
|---|---|---|
| [01 - Statistical Foundations](./01-statistical-foundations/) | Foundations | Population and sample, parameters and statistics, data types, sampling, study design, and the role of statistics |
| [02 - Descriptive Statistics](./02-descriptive-statistics/) | Summarising data | Measures of centre and spread, quartiles, IQR, outliers, distribution shape, z-scores, and the normal distribution |
| [03 - Data Visualization](./03-data-visualization/) | Exploring data visually | Choosing appropriate charts, reading distributions, comparing groups, and communicating patterns |
| [04 - Probability](./04-probability/) | Quantifying uncertainty | Probability rules, conditional probability, independence, counting, and related probability concepts |
| [05 - Inferential Statistics](./05-inferential-statistics/) | Learning from samples | Sampling distributions, standard error, the Central Limit Theorem, confidence intervals, and statistical inference |
| [06 - Statistical Tests](./06-statistical-tests/) | Testing claims | Hypothesis testing, p-values, significance, errors and power, parametric tests, and non-parametric tests |
| [07 - Regression and Relationships](./07-regression-and-relationships/) | Modelling relationships | Covariance, correlation, simple and multiple linear regression, least squares, residuals, diagnostics, multicollinearity, and prediction |
| [08 - Experimental Design and A/B Testing](./08-experimental-design-and-AB-testing/) | Measuring interventions | Study design, randomisation, confounding, metrics, sample size, power, significance testing, and practical interpretation of experiments |

---

## Learning sequence

The modules are arranged to build on one another:

```text
Statistical Foundations
        |
        v
Descriptive Statistics -----> Data Visualization
        |                           |
        v                           |
     Probability <------------------+
        |
        v
Inferential Statistics
        |
        v
  Statistical Tests
        |
        +----------------------+
        |                      |
        v                      v
Regression and          Experimental Design
Relationships           and A/B Testing
        |                      |
        +----------+-----------+
                   |
                   v
       Evidence-based data decisions
```

The sequence is intentional: first understand the data, then quantify uncertainty, then test claims or model relationships, and finally apply those methods to business and product decisions.

---

## Statistical methods covered

### Descriptive and exploratory analysis
- Measures of central tendency and dispersion
- Quartiles, percentiles, IQR, and outlier assessment
- Distribution shape, skewness, and the normal distribution
- Standardisation and z-scores
- Visual exploration and comparison of distributions

### Probability and inference
- Probability rules and conditional probability
- Sampling distributions and standard error
- Central Limit Theorem
- Confidence intervals for population parameters
- Hypothesis testing, p-values, significance levels, and decision errors
- Statistical power and sample-size considerations

### Statistical tests
- One-sample and two-sample tests for means
- Independent-samples and paired-samples t-tests
- One-sample and two-proportion z-tests
- One-way ANOVA
- Mann–Whitney U and Kruskal–Wallis tests
- Sign test and Spearman rank correlation
- Chi-square goodness-of-fit and test of independence

### Regression and relationships
- Covariance and Pearson correlation
- Correlation versus causation
- Simple and multiple linear regression
- Least-squares estimation and coefficient interpretation
- Residuals, residual plots, and regression diagnostics
- R-squared and adjusted R-squared
- Multicollinearity and variance inflation factor
- Model evaluation and prediction

### Experimental design and A/B testing
- Observational versus experimental studies
- Independent and dependent variables
- Control and treatment groups
- Randomisation, confounding, bias, and validity
- A/B test hypotheses and metric selection
- Primary and guardrail metrics
- Sample size, statistical power, and significance testing
- Practical significance and experiment interpretation

---

## Important statistical principles

1. A sample statistic is an estimate; it is not automatically equal to the population parameter.
2. A confidence interval describes the long-run performance of an interval-building procedure, not the probability that a fixed parameter lies in one already-computed interval.
3. A p-value is calculated under the null hypothesis. It is not the probability that the null hypothesis is true.
4. A result that is not statistically significant does not prove that there is no effect.
5. Statistical significance does not automatically imply practical importance.
6. Correlation does not establish causation.
7. A model that fits training data well may still perform poorly on unseen data.
8. Statistical conclusions are only as credible as the data quality, sampling process, experimental design, and assumptions behind the method.
