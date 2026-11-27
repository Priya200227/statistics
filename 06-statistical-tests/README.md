# 06 - Statistical Tests

> [!NOTE]
> 
> **Purpose:** A practical reference to selecting, understanding, implementing, and interpreting statistical tests used in data analysis.
>
> This folder is organised into **parametric** and **non-parametric** methods. The choice of a test depends on the research question, outcome type, study design, sampling process, and assumptions-not simply on whether a dataset looks normally distributed.

[← Back to Statistics Repository](https://github.com/Priya200227/statistics)

---

## 1. Where this folder fits

Statistical tests are part of **inferential statistics**. They use sample data to evaluate hypotheses about populations, compare groups, or assess relationships.

This folder builds on the concepts covered in the previous inferential-statistics section:

- Sampling distributions
- Statistical distributions
- Confidence intervals
- Hypothesis testing
- Significance levels and p-values
- Type I and Type II errors
- Statistical power

The aim here is to understand which test answers which question, what assumptions must be checked, how the test statistic is constructed, and how to interpret the result in a business or research context.

---

## 2. Test-selection guide

Start with the **outcome variable** and the **study design**. Do not choose a test based only on the number of columns or groups.

| Research question / data structure | Parametric method | Non-parametric or count-based method |
|---|---|---|
| Compare the means of two independent groups | Independent two-sample t-test (usually Welch's) | Mann–Whitney U test |
| Compare before-and-after measurements on the same subjects, or matched pairs | Paired-sample t-test | Sign test |
| Compare proportions from two independent groups | Two-proportion z-test | - |
| Compare the means of three or more independent groups | One-way ANOVA | Kruskal–Wallis test |
| Assess monotonic association between two ranked or ordinal variables | - | Spearman rank correlation |
| Compare observed counts with a specified categorical distribution | - | Chi-square goodness-of-fit test |
| Test association between two categorical variables | - | Chi-square test of independence |

**Important:** Chi-square tests are count-based procedures. They are commonly grouped with non-parametric methods in introductory learning plans, but they are not rank tests and have their own expected-count and sampling assumptions.

### Quick decision path

1. **Are you comparing groups, testing proportions, or measuring association?**
2. **Are the observations independent or paired/repeated?**
3. **Is the outcome quantitative, categorical, or ordinal?**
4. **Are the assumptions for the intended parametric test reasonable?**
5. Select the method that matches the design and question, then verify its conditions.

---

## 3. 01 - Parametric methods

Parametric tests evaluate hypotheses about population parameters such as means or proportions. Their reference distributions and standard errors rely on specified modelling assumptions.

**Open the detailed notes:** [01 - Parametric Methods](./01-parametric-methods/README.md)

### Topics covered

| Method | What it answers | Typical design |
|---|---|---|
| **Two-sample t-test (independent samples)** | Is there evidence that two independent population means differ? | Two unrelated groups |
| **Paired-sample t-test** | Is the population mean of paired differences different from a hypothesised value, usually zero? | Before/after or matched observations |
| **Two-proportion z-test** | Is there evidence that two independent population proportions differ? | Two independent groups with binary outcomes |
| **One-way ANOVA** | Is there evidence that at least one of three or more independent population means differs? | One categorical factor with 3+ groups and a quantitative outcome |

### Key ideas to understand

- Define the population parameter before writing hypotheses.
- Keep the null hypothesis and alternative hypothesis aligned with the research question.
- Distinguish independent samples from paired observations.
- Check randomisation/sampling, independence, distributional conditions, and variance assumptions where relevant.
- For two independent means, understand **Welch's t-test** and why it is generally a sensible default when equal population variances cannot be justified.
- For ANOVA, understand the F-statistic, between-group variation, within-group variation, and why a significant omnibus result requires follow-up comparisons to identify which groups differ.

---

## 4. 02 - Non-parametric methods

Non-parametric methods often use ranks, signs, or category counts rather than relying on a normal-theory model for population means.

They are useful for ordinal outcomes, skewed data, or situations where a rank-based or count-based question is more appropriate. They are **not assumption-free**: independence, sampling design, measurement scale, and method-specific conditions still matter.

**Open the detailed notes:** [02 - Non-parametric Methods](./02-non-parametric-methods/README.md)

### Topics covered

| Method | What it answers | Typical design |
|---|---|---|
| **Mann–Whitney U test** | Do two independent groups differ in their rank distributions / tendency to produce larger values? | Two independent groups |
| **Kruskal–Wallis test** | Does at least one of three or more independent groups differ in its rank distribution? | Three or more independent groups |
| **Sign test** | Is the population median, or median paired difference, different from a hypothesised value? | One sample or paired observations |
| **Spearman rank correlation** | Is there a monotonic association between two variables? | Paired observations measured on at least an ordinal scale |
| **Chi-square goodness-of-fit** | Do observed category counts follow a specified distribution? | One categorical variable |
| **Chi-square test of independence** | Are two categorical variables associated? | One population classified by two categorical variables |

### Important interpretation notes

- Mann–Whitney U and Kruskal–Wallis are not automatically tests of medians. A median/location interpretation is most defensible when group distributions have similar shapes and spreads.
- Kruskal–Wallis is an omnibus test. A significant result does not identify which groups differ; use suitable post-hoc comparisons with multiplicity adjustment.
- The sign test uses direction only and discards the magnitude of differences. Zero differences are excluded.
- Spearman measures monotonic association, not necessarily linear association, and does not establish causation.
- Chi-square procedures use observed and expected **counts**. Check expected cell/category counts before relying on the chi-square approximation.

---

## 5. A general hypothesis-testing workflow

Use this workflow for each test in this folder.

1. **Define the question.** State exactly what difference, association, or distributional claim is being investigated.
2. **Identify the design.** Determine whether groups are independent, paired, or repeated; identify the sampling unit.
3. **Define the parameter.** Examples include a difference in population means, a difference in proportions, a rank association, or a categorical distribution.
4. **State the hypotheses.** Write \(H_0\) and \(H_a\) using population parameters or the appropriate null model-not sample statistics.
5. **Choose \(\alpha\) in advance.** Do not select the significance level after seeing the p-value.
6. **Check assumptions and conditions.** Document which conditions are satisfied, violated, or assumed.
7. **Calculate the test statistic.** Use the method-specific formula or a trusted statistical implementation.
8. **Obtain the p-value.** Use the correct reference distribution and tail direction.
9. **Make the decision.**
   - If \(p \leq \alpha\), reject \(H_0\).
   - If \(p > \alpha\), fail to reject \(H_0\).
10. **Write a contextual conclusion.** Explain what the evidence says about the original question.
11. **Report practical importance.** Where appropriate, include an effect size, confidence interval, and group-level summaries.

### The correct interpretation of a p-value

A p-value is the probability, **assuming the null hypothesis and the test assumptions are true**, of obtaining a test statistic at least as extreme as the one observed.

It is not:

- The probability that the null hypothesis is true.
- The probability that the result happened “by chance.”
- The size or practical importance of an effect.

Failing to reject the null hypothesis does not prove that the null is true.

---

## 6. How to report a test result

A useful report should contain more than “significant” or “not significant.”

Include:

- The test name and why it matches the study design.
- The null and alternative hypotheses.
- Sample sizes and descriptive summaries.
- Relevant assumption checks.
- Test statistic and degrees of freedom, when applicable.
- Exact p-value (or a sensible bound such as \(p < 0.001\)).
- Significance level and decision.
- Effect size and confidence interval where appropriate.
- A conclusion written in the context of the question.

**Example reporting structure:**

> A [test name] was used to assess whether [population-level question]. The analysis produced [test statistic and degrees of freedom], with \(p = [value]\). At the preselected significance level of \(\alpha = [value]\), we [reject / fail to reject] the null hypothesis. The results provide [sufficient / insufficient] evidence that [contextual conclusion]. The estimated effect was [effect size], with [confidence interval, if available].

Do not use “accept the null hypothesis” as a substitute for “fail to reject the null hypothesis.”

---

## 7. Common mistakes

| Mistake | Better approach |
|---|---|
| Choosing a test because the data “looks non-normal” | Start with the research question, outcome type, and study design; then assess assumptions |
| Treating independent and paired samples as interchangeable | Identify whether observations are unrelated or linked/matched |
| Using a t-test for categorical counts | Use a proportion or categorical-data procedure that matches the question |
| Treating every rank-based test as a median test | Understand the distributional or stochastic-ordering interpretation |
| Assuming a significant ANOVA tells you which groups differ | Conduct suitable post-hoc comparisons with multiplicity control |
| Ignoring assumptions because a method is called non-parametric | Check independence, sampling, measurement scale, and test-specific conditions |
| Using percentages instead of counts in chi-square calculations | Use observed and expected counts |
| Interpreting \(p > \alpha\) as proof of no effect | Report that the evidence was insufficient to reject \(H_0\) |
| Interpreting statistical significance as business importance | Report effect size and practical context |
| Claiming causation from an observational association | Causal claims require an appropriate design and supporting assumptions |

---

## 8. Recommended learning order

Follow this order to build from two-group comparisons to multi-group tests and then categorical/rank-based association methods.

### 01 - Parametric methods

1. **Independent two-sample t-test**
   - Difference between two independent samples and paired samples
   - Hypotheses for a difference in means
   - Welch's standard error, t-statistic, and degrees of freedom
   - Conditions and interpretation
   - Python implementation

2. **Paired-sample t-test**
   - Identify matched/repeated observations
   - Calculate one difference per pair
   - One-sample t-test on the differences
   - Conditions and interpretation
   - Python implementation

3. **Two-proportion z-test**
   - Difference between two population proportions
   - Pooled proportion under the null hypothesis
   - Standard error, z-statistic, and p-value
   - Conditions and interpretation
   - Python implementation

4. **One-way ANOVA**
   - Between-group and within-group variation
   - Total, between, and within sums of squares
   - Mean squares and F-statistic
   - F-distribution and degrees of freedom
   - Assumptions and post-hoc comparisons
   - Python implementation

### 02 - Non-parametric methods

1. Mann–Whitney U test
2. Kruskal–Wallis test
3. Sign test
4. Spearman rank correlation
5. Chi-square goodness-of-fit test
6. Chi-square test of independence

For each method, learn the purpose, hypotheses, assumptions, statistic, p-value, interpretation, one worked example, and Python implementation. Avoid memorising formulas without understanding what the test compares.

---

## References

Use official documentation for implementation details and recognised statistical teaching resources for the underlying concepts.

### Python / SciPy documentation

- [SciPy statistical functions](https://docs.scipy.org/doc/scipy/reference/stats.html)
- [SciPy - t-tests and related functions](https://docs.scipy.org/doc/scipy/reference/stats.html#statistical-tests)
- [SciPy - Mann–Whitney U](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.mannwhitneyu.html)
- [SciPy - Kruskal–Wallis](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.kruskal.html)
- [SciPy - Binomial test](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.binomtest.html)
- [SciPy - Spearman correlation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)
- [SciPy - Chi-square goodness-of-fit](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.chisquare.html)
- [SciPy - Chi-square test of independence](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.chi2_contingency.html)

### Statistics learning resources

- [Penn State - STAT 200](https://online.stat.psu.edu/stat200/)
- [Penn State - STAT 500: Applied Statistics](https://online.stat.psu.edu/stat500/)

---

[← Back to Statistics Repository](https://github.com/Priya200227/statistics)

