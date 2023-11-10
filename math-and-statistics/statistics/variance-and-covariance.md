# Variance and Covariance

## Variance

Let $$X$$ be a random variable, $$\mu = \mathrm{E}[X]$$

Then

$$ \mathrm{var}(X) = \mathrm{E}[(X-\mu)^2] = \mathrm{E}[X^2-2X\mu+\mu^2] =\mathrm{E}[X^2]-\mu^2$$

## Covariance

Let $$X$$ and $$Y$$ be two jointly distributed random variables, $$\bar{X} = \mathrm{E}[X]$$ and $$\bar{Y} = \mathrm{E}[Y]$$

Then

$$ \mathrm{cov(X, Y)} = \mathrm{E}[(X-\bar{X})(Y-\bar{Y})]$$

Note

$$\mathrm{var}(X) = \mathrm{cov}(X,X)$$

### Covariance matrix

Let $$\mathbf{x}_i$$ be a vector of sample values for feature $$i$$ , and the matrix which contain all observations be

$$\mathbf{X} = [\mathbf{x}_1 \mathbf{x}_2 \dots \mathbf{x}_n]^\intercal$$

Let $$X_i$$ be the random variable for the outcome of feature $$i$$ 

Let $$\mathbf{C}_{\mathbf{X}}$$ be the covariance matrix

Then

The matrix's $$(i,j)$$ entry is defined as

$$c_{i,j} = \mathrm{cov}(X_i, X_j)$$

#### Property

$$
\begin{aligned}
\mathbf{C}_\mathbf{X} &= \frac{1}{N}\sum_i^N (x_i-\mu) (x_i - \mu) ^\intercal \\
&=\frac{1}{N}(\mathbf{X}-E_0(\mu))^T(\mathbf{X}-E_0(\mu))\\
&= \frac{1}{N}\mathbf{X}^\intercal \mathbf{X} -\mu_\mathbf{X} \mu_\mathbf{X}^\intercal
\end{aligned}
$$

where $$\mu_\mathbf{X}$$ is the vector of the sample means for each feature

Note that $$E_0$$ here represents an operation to expand the tensor along axis 0.

## Correlation

$$
\mathrm{corr}(\mathbf{X},\mathbf{Y})=\frac{\mathrm{cov}(\mathbf{X},\mathbf{Y})}{\sigma_x \sigma_y}
$$

