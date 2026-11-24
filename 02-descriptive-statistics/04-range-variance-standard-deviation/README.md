# Range, Variance, and Standard Deviation

## 1. Range

The range is the maximum value minus the minimum value.

$$
\text{Range}=x_{\max}-x_{\min}
$$

It is simple to calculate, but it depends only on two observations and is highly sensitive to outliers.

## 2. Variance

Variance measures the average squared deviation from the mean.

### Population variance

$$
\sigma^2=\frac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}
$$

### Sample variance

$$
s^2=\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
$$

The sample formula uses $n-1$, called **Bessel's correction**, for the usual unbiased estimator of population variance when the sample mean is used.

### Why square deviations?

- Positive and negative deviations do not cancel.
- Larger deviations receive more weight.
- The resulting units are squared (for example, dollars squared).

### Calculation sequence

1. Calculate the mean.
2. Subtract the mean from each observation.
3. Square each deviation.
4. Sum the squared deviations.
5. Divide by $N$ for population variance or $n-1$ for sample variance.

Example data: `[1, 2, 2, 3, 4, 5]`

$$
\mu=\frac{17}{6}\approx2.8333
$$

$$
\sigma^2=\frac{\sum(x_i-\mu)^2}{6}\approx1.8056
$$

## 3. Standard deviation

Standard deviation is the square root of variance.

$$
\sigma=\sqrt{\sigma^2}
\qquad
s=\sqrt{s^2}
$$

It is expressed in the same units as the original variable.

- Small SD: observations tend to be closer to the mean.
- Large SD: observations are more spread out around the mean.

The 68–95–99.7 rule applies to approximately normal distributions; it is not a guarantee for arbitrary data.

<LearningViz type_id="STANDARD_DEVIATION" />

## 4. Mean absolute deviation

Mean absolute deviation around the mean is:

$$
\mathrm{MAD}_{\mathrm{mean}}=
\frac{1}{n}\sum_{i=1}^{n}|x_i-\bar{x}|
$$

It measures average absolute distance in the original units.

The abbreviation MAD is also used for **median absolute deviation**:

$$
\mathrm{MAD}_{\mathrm{median}}=
\mathrm{median}\left(|x_i-\mathrm{median}(x)|\right)
$$

Always state which definition is being used.

## 5. Coefficient of variation

$$
CV=\frac{s}{|\bar{x}|}\times100\%
$$

CV expresses standard deviation relative to the mean. It can compare relative variability across ratio-scale measurements, but is unstable when the mean is near zero and is not suitable for interval-scale values such as Celsius temperatures.

## 6. Python implementation

```python
import pandas as pd

data = pd.Series([1, 2, 2, 3, 4, 5])

print("Range:", data.max() - data.min())
print("Population variance:", data.var(ddof=0))
print("Sample variance:", data.var(ddof=1))
print("Population SD:", data.std(ddof=0))
print("Sample SD:", data.std(ddof=1))
print("Mean absolute deviation:", (data - data.mean()).abs().mean())
```

In Pandas, `ddof=0` divides by $n$ and `ddof=1` divides by $n-1$. Set `ddof` explicitly because defaults differ between libraries.

## 7. Common mistakes

- Using $n$ instead of $n-1$ for the usual sample variance estimator.
- Forgetting that variance has squared units.
- Assuming one SD contains all or most observations in every distribution.
- Comparing CVs when the mean is near zero.
- Confusing mean absolute deviation with median absolute deviation.

## References

- [Krish Naik - Complete Statistics for Data Science](https://www.youtube.com/watch?v=LZzq1zSL1bs)
- [NumPy statistics routines](https://numpy.org/doc/stable/reference/routines.statistics.html)
- [Pandas descriptive statistics](https://pandas.pydata.org/docs/user_guide/basics.html#descriptive-statistics)

