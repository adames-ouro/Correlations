# Correlations

Correlation or dependence is any statistical relationship, whether causal or not. In the broadest sense, "correlation" may indicate any type of association.

Correlations are useful because they can indicate a predictive relationship that can be exploited in practice.

### Correlations: Pearson

In general, this coefficient (Pearson) can be interpreted as follows:
- **Magnitudes**:
    - .00-.19 `very weak`
    - .20-.39 `weak`
    - .40-.59 `moderate`
    - .60-.79 `strong`
    - .80-1.0 `very strong`
- **Sign**:
    - `positive` indicate a proportional relationship
    - `negative` indicate an inverse proportional relationship

Pearson's correlation has some mathematical assumptions in order to be used properly. These can be summarized as:
- Variables must be continuous.
- Data must be linear.
- Outliers affect the score.

It is defined as:

$$
Correlation = \frac{\sum{(X_{i} - X_{Ave}) \times (Y_{i} - Y_{Ave})}}{\sum{(X_{i} - X_{Ave})^2} \times \sum{(Y_{i} - Y_{Ave})^2}} 
$$


### Correlations: Spearman

Spearman does not assume a linear relationship nor restricts ordinal variables. 
It follows the same interpretation as the Pearson score.

It is defined as:

$$
Correlation = 1 - \frac{6 \times \sum{(X_{RANK} - Y_{RANK})^2}}{N \times (N^2-1)}
$$

where:
- N is the number of data points.

### Correlation: Cramér’s V

- Is a measure of association between two categorical features based on a nominal variation of Pearson’s Chi-Square Test.
- The output is in the range of [0,1], where 0 means no association and 1 is full association.
- The output matrix is also symmetrical, therefore assumes the same association for (x,y) and (y,x).
- Cramer’s V may lead to a loss of information due to the symmetry of it.

It is defined as:

$$
Correlation = \sqrt{\frac{\chi^2}{N \times MIN(k,l)}}
$$

where:
- $\chi^2$ is the chi-squared statistic.
- N is the sample size.
- k is the number of categories in the first variable.
- l is the number of categories in the second variable.

### Correlation: Theil’s U

- Theil’s U is a measure of the degree of inequality in a distribution.
- The output value is on the range of [0,1], with the same interpretations as before — but unlike Cramer’s V, it is asymmetric.
- It answers the following question: given the value of x, how many possible states does y have, and how often do they occur?
- Using Theil’s U will let us find out that knowing y means we know x, but not vice-versa.

It is defined as:

$$
Correlation = \frac{-\sum{P_{Xi} \times LOG(P_{Xi})} - (-\sum{P_{Yi} \times LOG(P_{Yi}))}}{LOG(N)}
$$

where:
- $P_{Xi}$ and $P_{Yi}$ are the probability of each value in the distributions X and Y.
- N is the number of values in the distribution.

### Correlation: Correlation Ratio

- The Correlation Ratio answers the following question: Given a continuous number, how well can you know to which category it belongs to? 
- Just like the two coefficients we’ve seen before, here too the output is on the range of [0,1].

It is defined as:

$$
Correlation = \frac{ \sum{{X}N_{X} \times (Y_{XAve} - Y_{Ave})^2} }{ \sum{{X,i}{(Y_{X,i} - Y_{Ave})^2} }}
$$

where:
- $Y_{Xi}$ is each observation where X indicates the category that observation is in and i is the label of observation.
- $N_{X}$ is the number of observations in category X.
- $\bar{Y}_{X}$ is the mean of the category X.
- $\bar{Y}$ is the mean of the whole population.


### Correlation: Time lagged cross correlation

- Time lagged cross correlation (TLCC) is a mathematical measure of similarity between two signals.
- This method holds one of the series in place and creates both lags of the second series across the time period before computing the correlation coefficients.
  
- For time series of the same length and no relative time delay, the definition is:

$$
Correlation_{XY}[0] = \sum_{n}{X[n] \times Y[n]}
$$

- For time series of different length and a relative time delay, the definition is:

$$
Correlation_{XY}[T] = \sum_{n}{X[n] \times Y[n-T]}
$$

where:
- $X[n]$ and $Y[n]$ are time series.
- $n$ is the number of observations in the series.
- $T$ is the time lag used to apply a relative time shift of the two sequences.
