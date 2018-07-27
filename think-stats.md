
# About

[Think Stats, 2nd Edition: Exploratory Data Analysis](http://shop.oreilly.com/product/0636920034094.do)
by Allen Downey
O'Reilly, 2014

# Thoughts

A practical, concise introduction to the subject with helpful Python tips. It cites good resources, but does not dig into the underlying math.

# Take-Aways

* Process for analyzing data: import and clean, single variable exploration, pair-wise exploration, multivariate analysis, estimation and hypothesis testing, visualization
* Common analytic distributions have methods for testing whether a given data set is a good fit, eg. Normal Probability Plot
* A good data set model may require applying different distributions for different data ranges, eg. Pareto for top 1% and lognormal for rest
* Python pitfall: attribute operator . is not the same as item operator [], see `__getattr__` vs `__getitem__`

Distribution Types Quadrant

```
                Discrete                Continuous

Cumulative      CDF / CMF    smooth->   CDF
                sum up / diff down      integrate up / differentiate down
Non-Cumulative  PMF          <-bin      PDF
```

# Concepts

* Analytic Distribution - CDF is a given formula, can be used to model an empirical distribution
* Behavioral Risk Factor Surveillance System (BRFASS) - CDC health survey
* Central Limit Theorem (CLT)
* Central Moment 2 - the variance
* Central Moment k = `sum(x**k for x in xs) / len(xs)`
* Codebook - study design doc with survey questions and response codings
* Cohen's Effect Size = (mean(x1) - mean(x2)) / pooled standard deviation
* Complementary CDF - CCDF(x) = 1 - CDF(x)
* Cross-Sectional Study - snapshot of a group
* Cumulative Distribution Funciton (CDF)
* Cumulative Mass Function - non-standard, perhaps more correct term for a CDF
* Current Population Survey (CPS) - study by the Bureau of Labor Stats and Census Bureau
* Deviation from the Mean = x[i] - mean(x)
* Discretizing - binning values
* Distribution - of a variable, frequency of values
* Empirical Distribution - from observed data
* Exponential Distribution - CDF(x) = 1 - e^-(lambda * x), test for fit by checking if CCDF(X) on a log-y scale is a line with slope -lambda
* Histogram - typical representation of a distribution
* Interarrival Times - time between events, tends to be an exponential distribution where events are equally likely at any time
* Interquantile Range - difference between 75th and 25th percentiles, a measure of spread
* Inverse Cumulative Distribution Function (ICDF) - transform a probability [0,1] into a value that fits the given distribution
* Kernel Density Estimation (KDE) - algorithm that fits PDF to data, useful for visualization, interpolation, simulation
* Lognormal Distribution - Lognormal_CDF(x) = CDF(log x)
* Longitudinal Study - repeated observations of a group over time
* Mean = sum(x) / len(x)
* Median - the 50th percentile
* Normal Distribution - aka Guassian distribution, bell curve, characterized by mean (mu) and standard deviation (sigma), CDF has a sigmoid shape, use Normal Probability Plot to test for fit
* Normal Probability Plot - method to test how closely data fits a normal distribution, graphs values against random sample from the normal distribution, good fit is a line with intercept mean and standard deviation slope
* Normalization - convert frequencies to probabilities
* Oversampled Study - selected subpopulations are more heavily represented
* Pareto Distribution - used by economist Vilfredo Pareto to model distribution of wealth, typical of preferential attachment processes, CDF Pareto(x) = 1 - (x / min(x))^(-alpha), fit test: CCDF is a straight line on a log-log scale
* Percentile - value corresponding to a given percentile rank
* Percentile Rank - percent of values less than or equal to given value
* Probability Density Function (PDF) - derivative of CDF
* Probability Mass Function (PMF) - map value to probability of it occurring, may require binning for fine grained values but watch for aliasing issues
* Quantile - sequence of values corresponding to equally spaced percentile ranks
* Quantizing - binning values
* Raw Moment 1 - the mean
* Raw Moment k = `sum(x**k for x in xs) / len(xs)`
* Re-codes - calculated variables, not part of the raw data
* Replacement - "with replacement" means a value can be sampled more than once, "without replacement" means that chosen values are immediately removed from the population
* Representative Study - each member of the population has equal chance to participate
* Sample Skewness - the 3rd Standardized Moment, tends to be disproportionately affected by outliers
* Sigmoid Curve - S-shaped curve
* Skewness - describes of the shape of a distribution, unskewed implies symmetric about the central tendency
* Standard Deviation = sqrt(variance)
* Standard Normal Distribution - has mean = 0 and standard deviation = 1
* Standardized Moment k = Central Moment k / Standard Deviation ^ k
* Uniform Distribution - flat curve, values evenly distributed
* Variance = sum(x.map(i => (i - mean(x))^2) / len(x)
* Weibull Distribution - generalized exponential distribution, typical of failure analysis

# Techs

* Anaconda Python (python stats distro)
* IPython (Jupyter kernel)
* Jupyter Notebook (data analytics)
* Matplotlib (python lib)
* Numpy (python lib)
* Pandas (python lib) - Python Data Analysis Library
* PlasTeX (python LaTeX framework)
* pyplot (python lib)
* Python collections (container types lib)
* SciPy (python lib)
* Stata (data analytics)
* StatsModels (python lib)

# Code Clips

```
# replace not-applicable values so as not to bias results
array.replace([na_values], numpy.nan, inplace=True)
```

```
# typical conversion of data set to histogram
counts = {}
for value in data:
	counts[value] = counts.get(value, 0) + 1
```

```
# normalization of distribution
probability[x] = counts[x] / len[x]
```

```
# random exponential distribution value
def expovariate(lam):
	p = random.random()
	return -math.log(1-p) / lam
```

* `collections.Counter`
* `pandas.Series.value_counts`
* `scipy.stats.norm.cdf`
* `del data[x]` - remove from dictionary
* `zip(*data)` - unzip (zip, splat)
* `**` - pow operator

# Futher Reading

* Cecil Adams, The Straight Dope
* Reddit /r/statistics
* Wikipedia stats pages
* Wolfram MathWorld
