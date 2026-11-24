# Mean, Median, and Mode

[← Back to Descriptive Statistics Repository](https://github.com/Priya200227/statistics/tree/main/02-descriptive-statistics)

## 1. Arithmetic mean

The arithmetic mean is the sum of observations divided by the number of observations.

### Population mean

$$
\mu = \frac{\sum_{i=1}^{N}x_i}{N}
$$

### Sample mean

$$
\bar{x} = \frac{\sum_{i=1}^{n}x_i}{n}
$$

- $x_i$: an observed value
- $N$: population size
- $n$: sample size
- $\mu$: population mean
- $\bar{x}$: sample mean

**Example:** For `[1, 1, 2, 2, 3, 3, 4, 5, 5, 6]`:

$$
\bar{x}=\frac{32}{10}=3.2
$$

### Weighted mean

A weighted mean gives observations different levels of influence.

$$
\bar{x}_w = \frac{\sum_{i=1}^{k}w_ix_i}{\sum_{i=1}^{k}w_i}
$$

Example: a course grade has an assignment score of 80 weighted at 30% and an exam score of 90 weighted at 70%.

$$
0.30(80)+0.70(90)=87
$$

Use weighted means when observations have different importance, exposure, frequency, or denominators.

## 2. Median

The median is the middle observation after sorting values in ascending order.

- If $n$ is odd, select the observation at position $(n+1)/2$.
- If $n$ is even, average the observations at positions $n/2$ and $n/2+1$.

Odd sample:

$$
\text{Median}=x_{((n+1)/2)}
$$

Even sample:

$$
\text{Median}=\frac{x_{(n/2)}+x_{(n/2+1)}}{2}
$$

### Why the median is resistant to extreme values

Original data:

`[1, 1, 2, 2, 3, 3, 4, 5, 5, 6]`

- Mean = 3.2
- Median = 3

Add 100:

`[1, 1, 2, 2, 3, 3, 4, 5, 5, 6, 100]`

- Mean = 12
- Median = 3

The mean moves substantially, while the median remains unchanged in this example.

## 3. Mode

The mode is the most frequently occurring value or category.

- **Unimodal:** one mode
- **Bimodal:** two modes
- **Multimodal:** more than two modes
- **No unique mode:** no value occurs more frequently than the others

Example: `[1, 2, 3, 4, 5, 6, 6, 6, 7, 8]` has mode 6.

Mode is useful for categorical data such as product category, payment method, or flower type.

## 4. Compare the measures

| Situation | Measure to consider |
|---|---|
| Symmetric numerical data without major outliers | Mean |
| Skewed numerical data | Median |
| Categorical variable | Mode |
| Unequal weights or group sizes | Weighted mean |
| Multiple peaks | Inspect the full distribution |

## 5. Python implementation

```python
import pandas as pd

data = pd.Series([1, 1, 2, 2, 3, 3, 4, 5, 5, 6])

mean_value = data.mean()
median_value = data.median()
mode_values = data.mode()

print(mean_value, median_value, mode_values.tolist())
```

## 6. Common mistakes

- Calculating the median before sorting.
- Treating the mean as the best summary in every situation.
- Assuming a dataset has exactly one mode.
- Averaging subgroup averages without accounting for group sizes.
- Interpreting the percentile as a percentage score rather than a position in a distribution.

## References

- [Krish Naik - Complete Statistics for Data Science](https://www.youtube.com/watch?v=LZzq1zSL1bs)
- [Pandas descriptive statistics](https://pandas.pydata.org/docs/user_guide/basics.html#descriptive-statistics)

