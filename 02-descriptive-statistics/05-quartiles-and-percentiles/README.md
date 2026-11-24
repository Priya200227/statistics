# Quartiles and Percentiles

[← Back to Descriptive Statistics Repository](https://github.com/Priya200227/statistics/tree/main/02-descriptive-statistics)

---

## 1. Percentiles

The $p$-th percentile is a value at or below which approximately $p\%$ of observations lie, according to the selected quantile convention.

Examples:

- 25th percentile = Q1.
- 50th percentile = Q2 (median).
- 75th percentile = Q3.
- 90th percentile = a threshold at or below which approximately 90% of observations fall.

If a candidate's score is at the 80th percentile, this describes a position relative to the comparison group. It does **not** mean the candidate scored 80%.

## 2. Percentile rank vs percentile value

These answer different questions:

- **Percentile rank:** What percentage of observations are below (or at/below) a particular value?
- **Percentile value / quantile:** What value marks a specified percentage of the distribution?

One empirical percentile-rank convention is:

Let `N_below_x` be the number of observations in the dataset that are strictly less than the value `x`.

$$
\mathrm{PercentileRank}(x)=\frac{N_{\mathrm{below}\ x}}{n}\times100
$$

This uses the strict-less-than convention. Ties and alternative definitions (less-than-or-equal, midrank, interpolation) produce different results. It is not a universal software standard.

## 3. Quartiles

Quartiles divide ordered data into four parts:

- Q1: 25th percentile.
- Q2: 50th percentile (median).
- Q3: 75th percentile.

![Quartiles and interquartile range](../images/03-quartiles-and-boxplots/quartiles-iqr-boxplot.png)

Quantile algorithms differ in how they interpolate between observations. NumPy and Pandas provide method options; state the method when exact reproducibility matters.

## 4. Python implementation

```python
import pandas as pd

data = pd.Series([1, 2, 2, 3, 3, 4, 5, 5, 5, 6])

q1 = data.quantile(0.25)
q2 = data.quantile(0.50)
q3 = data.quantile(0.75)

print({"Q1": q1, "Q2": q2, "Q3": q3})
```

For a reproducible analysis, record the quantile interpolation/method choice where it matters.

## 5. Business applications

- Employee performance percentiles.
- Customer spending thresholds.
- Delivery-time service levels.
- Exam scores and benchmark comparisons.
- Revenue segmentation.

## 6. Common mistakes

1. Confusing percentile rank with percentile value.
2. Saying the 80th percentile means an 80% score.
3. Assuming all tools calculate quantiles identically.
4. Ignoring ties and the chosen percentile-rank convention.


## References

- [Krish Naik - Complete Statistics for Data Science](https://www.youtube.com/watch?v=LZzq1zSL1bs)
- [Pandas quantile documentation](https://pandas.pydata.org/docs/reference/api/pandas.Series.quantile.html)
