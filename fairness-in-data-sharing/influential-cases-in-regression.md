# Detecting Influential Cases in Regression

## Empirical influence function

In the context of the linear model

$$
Y=X\beta + e
$$

Let $$\hat{\beta}$$be the usual lest squares estimator of $$\beta$$based on the full data and let $$\hat{\beta}_A$$be an alternative least squares estimator based on a subset of the data. The empirical influence function for $$\hat{\beta}$$, $$IF_A$$is defined by

$$
IF_A = \hat{\beta}_A-\hat{\beta}
$$

## Characterisation of the empirical influence function

$$IF_A$$can be characterised by the distance between $$\hat{\beta}$$and $$\hat{\beta}_A$$\[[1](influential-cases-in-regression.md#references)\].

Let $$M$$be a given positive \(semi\) definite matrix, and $$c$$be a nonzero scale factor, the distance between $$\hat{\beta}$$and $$\hat{\beta}_A$$is defined by

$$
D_A(M,c) = \frac{(IF_A)^TM(IF_A)}{c}
$$

The matrix $$M$$can be chosen to reflect specific interests.

## Case analysis of the distance measures

### Deleting one case at a time

The larger $$D_i(M,c)$$is, the more influential case $$i$$is.

### Deleting several cases at a time

## References

1. R. D. Cook and S. Weisberg, “Characterizations of an Empirical Influence Function for Detecting Influential Cases in Regression,” Technometrics, vol. 22, no. 4, pp. 495–508, 1980, doi: [10.1080/00401706.1980.10486199](https://doi.org/10.1080/00401706.1980.10486199)
2. “Outlier Diagnostics,” Robust Regression and Outlier Detection Wiley Series in Probability and Statistics, pp. 216–247, 2005, doi: [10.1002/0471725382](https://doi.org/10.1002/0471725382)



