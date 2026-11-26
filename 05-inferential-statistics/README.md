# 05 --- Inferential Statistics

Inferential statistics uses information from a sample to draw
conclusions about a larger population. It helps us estimate unknown
population parameters, quantify uncertainty, and evaluate claims using
statistical evidence.

This folder documents the core concepts and methods of inferential
statistics, with an emphasis on understanding when to use a method,
checking its assumptions, interpreting its results, and applying it to
practical data-analysis problems.

------------------------------------------------------------------------

## Learning objectives

By completing this section, you should be able to:

-   Explain how sample information is used to make inferences about a
    population.
-   Understand sampling distributions and the role of probability
    distributions in statistical inference.
-   Estimate population parameters using confidence intervals.
-   Formulate and evaluate statistical hypotheses.
-   Interpret p-values, significance levels, confidence intervals, and
    test conclusions correctly.
-   Recognise the assumptions and limitations behind common inferential
    procedures.
-   Connect statistical results to practical analytical questions
    without overstating what the data proves.

------------------------------------------------------------------------

## Folder structure

``` text
05-inferential-statistics/
│
├── 01-statistical-distributions/
│   └── README.md
│
├── 02-confidence-intervals/
│   └── README.md
│
├── 03-hypothesis-testing/
│   └── README.md
│
└── README.md
```

------------------------------------------------------------------------

## 01 --- Statistical Distributions

**Status: Completed**

This section covers probability distributions and sampling distributions
that provide the foundation for statistical inference.

Topics include:

-   Probability distributions and their role in statistics
-   Normal distribution and the standard normal distribution
-   Z-scores and standardisation
-   Sampling distributions
-   Central Limit Theorem
-   Sampling distribution of the sample mean and sample proportion
-   Standard error and how sample size affects sampling variability
-   Student's t-distribution and degrees of freedom

[Open Statistical
Distributions](./01-statistical-distributions/README.md)

------------------------------------------------------------------------

## 02 --- Confidence Intervals

**Status: Completed**

Confidence intervals use sample data to estimate an unknown population
parameter while expressing the uncertainty associated with that
estimate.

Topics include:

-   Point estimates and interval estimates
-   Confidence level and margin of error
-   Confidence interval for a population mean
-   Z-interval and t-interval
-   Confidence intervals using paired data
-   Degrees of freedom
-   Sample size and margin of error
-   Correct interpretation of confidence intervals
-   Conditions and limitations of interval estimation

[Open Confidence Intervals](./02-confidence-intervals/README.md)

------------------------------------------------------------------------

## 03 --- Hypothesis Testing

**Status: Completed**

Hypothesis testing provides a structured way to evaluate claims about
population parameters using sample evidence.

Topics include:

-   Null and alternative hypotheses
-   One-tailed and two-tailed tests
-   Significance level and p-value
-   Type I and Type II errors
-   Statistical power
-   One-proportion z-test
-   One-sample t-test for a population mean
-   Z-statistics vs. t-statistics
-   Critical-value and p-value approaches
-   Conditions, decisions, and contextual conclusions

[Open Hypothesis Testing](./03-hypothesis-testing/README.md)

------------------------------------------------------------------------

## Next sections in the statistics roadmap

The following folders extend the foundations above into commonly used
statistical methods and analytical applications. They are planned next
steps, not completed sections.

### 06 --- Statistical Tests

A practical reference for selecting, applying, and interpreting
statistical tests.

Planned structure:

``` text
06-statistical-tests/
│
├── 01-parametric-methods/
│   ├── two-sample-t-test/
│   ├── paired-t-test/
│   ├── two-proportion-z-test/
│   └── anova/
│
├── 02-non-parametric-methods/
│   ├── mann-whitney-u-test/
│   ├── wilcoxon-signed-rank-test/
│   ├── kruskal-wallis-test/
│   ├── friedman-test/
│   ├── sign-test/
│   ├── chi-square-goodness-of-fit/
│   └── chi-square-test-of-independence/
│
└── README.md
```

The classification is practical rather than absolute: chi-square
procedures are tests for categorical frequency data and are commonly
grouped with non-parametric methods. Spearman rank correlation will be
documented primarily with non-parametric methods and cross-referenced
from regression and relationships.

### 07 --- Regression and Relationships

Study relationships between variables and use regression models to
quantify and interpret those relationships.

Planned topics:

-   Covariance
-   Pearson correlation
-   Spearman rank correlation (cross-reference)
-   Simple linear regression
-   Multiple linear regression
-   Regression coefficients and their interpretation
-   R-squared and adjusted R-squared
-   Regression assumptions and diagnostics
-   Residual analysis
-   Multicollinearity
-   Inference for regression coefficients
-   Confidence intervals and prediction intervals

### 08 --- Experimental Design and A/B Testing

Study how experiments are designed and how statistical evidence is used
to evaluate interventions and product or business changes.

Planned topics:

-   Observational studies vs. experiments
-   Random assignment and randomisation
-   Control and treatment groups
-   Confounding variables and bias
-   A/B testing fundamentals
-   Hypotheses in A/B tests
-   Sample size and statistical power
-   Conversion-rate experiments
-   Statistical vs. practical significance
-   Multiple testing considerations
-   Experiment interpretation and reporting

------------------------------------------------------------------------

## How each topic will be documented

To keep the repository consistent and useful as a reference, each method
or concept will follow a common structure where applicable:

1.  **Concept and purpose** --- what the method does and the problem it
    addresses.
2.  **When to use it** --- the type of question and data it is designed
    for.
3.  **Hypotheses or estimand** --- the population parameter or effect
    being investigated.
4.  **Assumptions and conditions** --- what must be checked before
    applying the method.
5.  **Formula and intuition** --- the mathematical expression and what
    its components mean.
6.  **Worked example** --- a step-by-step numerical example.
7.  **Python implementation** --- practical implementation using
    relevant libraries such as SciPy, NumPy, pandas, and statsmodels.
8.  **Interpretation** --- how to explain the result in statistical and
    real-world terms.
9.  **Common mistakes and limitations** --- what the method cannot
    establish and how it is often misused.
10. **Visual reference** --- a diagram or chart where it improves
    understanding.

Not every topic requires every item. The documentation should remain
focused on the method rather than forcing a template where it adds no
value.

------------------------------------------------------------------------

## Important distinction

Inferential statistics does not eliminate uncertainty or automatically
make a sample representative of a population. The quality of an
inference depends on the sampling or experimental design, the
assumptions of the method, the quality of the data, and the
interpretation of the result.

A statistically significant result is not automatically practically
important, and statistical association alone does not establish
causation.

------------------------------------------------------------------------

## Scope of this section

This repository focuses on the inferential statistics concepts and
methods most useful for practical data analysis. Advanced topics such as
Bayesian modelling, extensive resampling theory, and specialised
causal-inference methods are outside the current core scope and can be
added later if a project or learning goal requires them.

------------------------------------------------------------------------

## Progress tracker

  Section                                      Status
  -------------------------------------------- -----------
  01 --- Statistical Distributions             Completed
  02 --- Confidence Intervals                  Completed
  03 --- Hypothesis Testing                    Completed
  06 --- Statistical Tests                     Planned
  07 --- Regression and Relationships          Planned
  08 --- Experimental Design and A/B Testing   Planned

