
# About

* [Think Stats, 2nd Edition: Exploratory Data Analysis](http://shop.oreilly.com/product/0636920034094.do)
* by Allen Downey
* published by O'Reilly, 2014

# Thoughts

A practical, concise introduction to the subject with helpful Python tips. It cites good resources, but does not dig very deep into the underlying math. As stated in the book, the emphasis is on computational methods (resampling, permutation) over analytic methods (basically, relying on formulae.)

# Take-Aways

* Process for analyzing data: import and clean, single variable exploration, pair-wise exploration, multivariate analysis, estimation and hypothesis testing, visualization
* Computational methods can be slow but have advantages over analytic methods: easier to reason about, robust, adaptable, debuggable
* Common analytic distributions have methods for testing whether a given data set is a good fit, eg. Normal Probability Plot
* A good data set model may require applying different distributions for different data ranges, eg. Pareto for top 1% and lognormal for rest
* Line graphs representing the 25th, 50th, and 75th percentiles (or some similar spread) can help visualize data contours
* Sample mean and sample standard deviation can be used as hypothetical values to simulate error values
* A trick for modelling the null hypothesis is to shuffle sample groups together to create a neutral group and run selection experiments on it; do the random selections exhibit a stronger test statistic than what we are trying to verify?
* In hockey the time between goals is roughly exponential; can simulate the goals scored per game by running an exponential function until the total time between goals scored exceeds the length of the game
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
* Autocorrelation Function - maps lag to serial correlation
* Behavioral Risk Factor Surveillance System (BRFASS) - CDC health survey
* Categorical Variable - non-numerical values, like an enum
* Central Limit Theorem (CLT) - the sum of n values, taken independently from a distribution with finite mean and variance, converges to normal as n increases; exponential distributions converge quickly, lognormal distributions converge slowly
* Central Moment 2 - the variance
* Central Moment k = `sum(x**k for x in xs) / len(xs)`
* Chi-Squared - commonly test statistic, = `sum((observed - expected)^2 / expected)`, indicates a difference between groups but not what the diff is
* Classical Hypothesis Testing - commonly used methods; Fisher null hypothesis testing, Neyman-Pearson decision theory, and Bayesian inference
* Codebook - study design doc with survey questions and response codings
* Coefficient of Determination, aka R-squared - a measure of goodness of fit, the square of the Pearson's Coefficient of Correlation; a better indicator of reduction in MSE, and reduction in RMSE is a better indicator of predictive power; can be used as a test statistic with no slope to model a null hypothesis
* Cohen's Effect Size = (mean(x1) - mean(x2)) / pooled standard deviation
* Cohort Effects - observable differences between cohorts
* Cohorts - groups defined by some event or criteria eg. year of birth
* Complementary CDF - CCDF(x) = 1 - CDF(x)
* Confidence Interval - range around the median of sampling distribution, eg. the 90% confidence interval is the range from the 5th percentile to the 95th percentile; plotting confidence intervals can visualize error in y-intercept and slope of fitted line
* Control Variable - grouping results by a control variable isolates other variables to see if they have an effect; compares like-to-like data
* Correlation - quantifies the strength of relationship between two variables, but beware of differing units
* Covariance - tendency for two variables to vary together; the dot product of variable deviations, divided by their length; units are hard to interpret (product of x and y units); `covariance(X, Y) = (1/n) * Sum(dx, dy)` where dx, dy are differences from the mean; `cov = np.dot(xs - meanx, xy - meany) / len(xs)`
* Cross-Sectional Study - snapshot of a group
* Cumulative Distribution Funciton (CDF)
* Cumulative Mass Function - non-standard, perhaps more correct term for a CDF
* Current Population Survey (CPS) - study by the Bureau of Labor Stats and Census Bureau
* Dependent / Endogenous Variables - set of variables influenced by a given set of explanatory variables; the effects in a relationship between variables
* Deviation from the Mean = x[i] - mean(x)
* Discretizing - binning values
* Distribution - of a variable, frequency of values
* Empirical Distribution - from observed data
* Explanatory / Exogenous / Independent Variables - set of variables that influences a given set of dependent variables; the causes in a relationship between variables
* Exponential Distribution - CDF(x) = 1 - e^-(lambda * x), test for fit by checking if CCDF(X) on a log-y scale is a line with slope -lambda
* Exponentially-Weighted Moving Average (EWMA) - most recent value has highest weight, the weight drops off exponentially
* Goodness of Fit - measure of the quality of a linear model
* Hazard Function - maps duration to probability that any duration will be that long (in that duration bucket)
* HexBin plot - clusters data into hexagonal cells to depict density; efficient for large sets but may obscure outliers
* Histogram - typical representation of a distribution
* Hypothesis Testing - given a sample and an apparent effect, what is the probability that the effect arose by chance?
* Interarrival Times - time between events, tends to be an exponential distribution where events are equally likely at any time
* Interquantile Range - difference between 75th and 25th percentiles, a measure of spread
* Inverse Cumulative Distribution Function (ICDF) - transform a probability [0,1] into a value that fits the given distribution
* Jittering - adding noise to data to reverse the effects of rounding, useful for visualization
* Kaplan Meier Estimation - algorithm used to estimate a hazard function from given data
* Kernel Density Estimation (KDE) - algorithm that fits PDF to data, useful for visualization, interpolation, simulation
* Lag - interval to shift time for serial correlation
* Linear Least Squares Fit - model a relationship assuming constant slope, produces a fit with minimal MSE, is computationally efficient
* Linear Regression - the relationship between dependent and explanatory variables is linear
* Logistic Regression - boolean dependent variable, uses log of the linear model, no closed form solution so requires iterating on guesses (see Newton's Method), StatsModels implementation is called `logit`
* Lognormal Distribution - Lognormal_CDF(x) = CDF(log x)
* Longitudinal Study - repeated observations of a group over time
* Maximum Likelihood Estimator (MLE) - estimate the value with the best odds; `L = 1/mean`, biased estimator of exponential distributions
* Mean = `sum(x) / len(x)`
* Mean Squared Error (MSE) = `(1/m) * Sum(sample_mean - mean)^2`, m is the number of times a sample is taken
* Measurement Error - bias introduced by the measuring process
* Median - the 50th percentile
* Moving Average - divides a series into overlapping windows, calculates average for each window
* Multiple Regression - more than one explanatory variable
* Multivariate Regression - more than one dependent variable
* Natural Experiment - uses a naturally occurring grouping of subjects that is approximately random
* New Better Than Used In Expectation (NBUE) - new part is expected to last longer than used; having survived some means future survival is less likely
* Newton's Method - an iterative solver used by many stats packages for logistic regression
* Normal Distribution - aka Guassian distribution, bell curve, characterized by mean (mu) and standard deviation (sigma), CDF has a sigmoid shape, use Normal Probability Plot to test for fit
* Normal Probability Plot - method to test how closely data fits a normal distribution, graphs values against random sample from the normal distribution, good fit is a line with intercept mean and standard deviation slope
* Normalization - convert frequencies to probabilities
* Null Hypothesis - model that assumes an apparent effect is not real, eg. two groups have the same distribution
* Odds in Favour - ratio of the probability that an event will occur to the probably that it will not; `o = p / (1-p)`
* Ordinary Least Squares (OLS) - a method for fitting a linear model, StatsModels has an ols() constructor for this
* Oversampled Study - selected subpopulations are more heavily represented; can be corrected for by resampling with weights
* p-value - probability of seeing an apparent effect when the null hypothesis is true, eg. the probability that the mean of two samples differs due to sampling error; when p-value is low, the effect is said to be statistically significant; p-value of 0.05 is an arbitrary choice, suitability depends on the test statistic and null hypothesis used; consider interpreting p-values by order of magnitude; p-value observed depends on what test statistic is used (eg. total deviation vs chi-squared)
* Pareto Distribution - used by economist Vilfredo Pareto to model distribution of wealth, typical of preferential attachment processes, `CDF Pareto(x) = 1 - (x / min(x))^(-alpha)`, fit test: CCDF is a straight line on a log-log scale
* Pearson Product-Moment Correlation Coefficient - values mapped to standard deviations from the mean for correlation
* Pearson's Correlation - divides deviations by standard deviation to strip away units, returns a correlation score in the range [-1, 1], only measures linear relationships so non-linear relationships will be understated
* Percentile - value corresponding to a given percentile rank
* Percentile Rank - percent of values less than or equal to given value
* Poisson Regression - integer count dependent variable
* Probability Density Function (PDF) - derivative of CDF
* Probability Mass Function (PMF) - map value to probability of it occurring, may require binning for fine grained values but watch for aliasing issues
* Proxy Variable - dependent on data not included in the study; acts like an explanatory variable because it is itself a dependent of the true causes
* Quantile - sequence of values corresponding to equally spaced percentile ranks
* Quantizing - binning values
* Randomized Controlled Trial - subjects assigned randomly to groups; uses a control group
* Raw Moment 1 - the mean
* Raw Moment k = `sum(x**k for x in xs) / len(xs)`
* Re-codes - calculated variables, not part of the raw data
* Regression - fitting a model to data; StatsModels provides several methods
* Replacement - "with replacement" means a value can be sampled more than once, "without replacement" means that chosen values are immediately removed from the population
* Replication - separate data sets should be used for hypothesis exploration and verification, otherwise there is a risk of generating a false positive result
* Representative Study - each member of the population has equal chance to participate
* Residual - vertical deviation from the linear fit line; if residuals are uncorrelated and normally distributed about 0, then linear least squares is the maximum likelihood estimator of y-intercept and slope; plotting residuals of the 25th, 50th, and 75th percentiles is a visualization of fit where curvature indicates that the relationship is non-linear
* Rolling Mean - computes mean of values in each window; Pandas provides a `rolling_mean` function
* Root Mean Squared Error (RMSE) = sqrt(MSE)
* Sample Skewness - the 3rd Standardized Moment, tends to be disproportionately affected by outliers
* Sample Variance (S2) = `(1/n) * Sum(xi - sample_mean)^2`, biased estimator, tends to be too low for small samples; `S2(n-1) = (1/(n-1)) & Sum(xi - sample_mean)^2` is an unbiased estimator
* Sampling Bias - when the sampling process favours a subpopulation
* Sampling Distribution - generated by sampling from an estimator
* Sampling Error - variation in an estimate caused by random selection
* Saturation - overlapping data points, can be depicted visually as colour / heat
* Scatter Plot - most simple visualization of a relationship between two variables; excellent starting point to check for correlations
* Seasonality - patterns in the data that repeat over time
* Self-Selection - type of sampling bias where participants opt-out
* Serial Correlation - each value is correlated with the next one in the series
* Sigmoid Curve - S-shaped curve
* Simple Regression - one dependent and one explanatory variable
* Skewness - describes of the shape of a distribution, unskewed implies symmetric about the central tendency
* Spearman Rank Correlation Coefficient - values mapped to ranks for correlation; mitigates outliers and skewed distributions
* Standard Deviation = sqrt(variance)
* Standard Deviation of Residuals - simple measure of goodness of fit
* Standard Error (SE) - how much we expect an average estimate to be off by, see RSME; common pitfall to confuse standard deviation with standard error; standard error decreases as sample size increases, whereas standard deviation does not
* Standard Normal Distribution - has mean = 0 and standard deviation = 1
* Standardized Moment k = Central Moment k / Standard Deviation ^ k
* Stationary System - constant model parameters over time, eg. constant slope, intercept, and distribution of residuals
* Statistically Significant -  does not mean that the effect is large, only that it is unlikely to have occurred by chance
* Survival Analysis - study duration until an event, eg. probability of surviving for a given length of time
* Survival Curve - maps duration to probability of surviving at least that long; complement of the distribution of durations
* Test Power / Sensitivity - effect size that a test can measure; when positive results are common (base rate) the test is "underpowered;" rule of thumb power of 80% is considered acceptable
* Test Statistic - size of an apparent effect, eg. difference in mean between two groups
* Time Series - sequence of measurements over time, eg. hockey stick graph of global average temperature
* Total Deviation - sum of the deviations from mean, can be used as a test statistic
* Trivers-Willard Hypothesis - supposes that for many mammals the sex ratio depends on maternal condition
* Two-Sided Test Statistic - considers both sides of a distribution, eg. magnitude only, absolute value of a measure
* Unbiased Estimator - expected error after many iterations is 0
* Uniform Distribution - flat curve, values evenly distributed
* Used Better Than New In Expectations (UBNE) - used part is expected to last longer than new; having survived some means that future survival is more likely
* Variance = `sum(x.map(i => (i - mean(x))^2) / len(x)`
* Weibull Distribution - generalized exponential distribution, typical of failure analysis
* Zachary M. Jones - political science researcher

# Techs

* Anaconda Python (python stats distro)
* IPython (Jupyter kernel)
* Jupyter Notebook (data analytics)
* Matplotlib (python lib)
* Numpy (python lib)
* Pandas (python lib) - Python Data Analysis Library
* Patsy (StatsModels formula parser)
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

* Data Analysis with Open Source Tools - Philipp Janert book, covers time series analysis and autoregression
* Reddit /r/statistics
* The Straight Dope - Cecil Adams web site
* Think Bayes - Allen Downey book
* Wikipedia stats pages
* Wolfram MathWorld
