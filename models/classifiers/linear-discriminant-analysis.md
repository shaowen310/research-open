# Linear Discriminant Analysis

## Symbols

| Symbol | Description |
| :--- | :--- |
| $$E_i(x)$$ | Expand tensor x along axis i |
| $$C$$ | Cluster set |
| $$n_i$$ | The number of elements in cluster i |

## LDA

### Between-class scatter matrix

#### Two class case

\(Fisher, 1936\)

$$
S_b = (\mu_1-\mu_2)(\mu_1-\mu_2)^\intercal
$$

#### Multiclass clase

\(Johnson & Wichern, 1988\)

$$
S_b=\sum_{i\in C}n_i(\mu_i - \mu)(\mu_i-\mu)^\intercal
$$

### Within-class scatter matrix

$$
\begin{aligned}
S_w &= \sum_{i \in C} \sum_{x \in X_i}(x-\mu_i)(x-\mu_i)^\intercal \\
&= \sum_{i\in C}(X_i-E_0(\mu_i))^\intercal (X_i-E_0(\mu_i)) \\
&=\sum_{i\in C} (X^\intercal X - n_i \mu_i \mu_i^\intercal) \\
&=\sum_i^n (x_i-\mu_{y_i})(x_i-\mu_{y_i})^\intercal\\
&=(X-M)^\intercal(X-M)
\end{aligned}
$$

Suppose the corresponding row of the ith row of $M$ is $x\_i$ and $y\_i$ is $x\_i$'s label, then the ith row of $M$ is $\mu\_{y\_i}$.

### Optimisation problem

Find $w$ s.t.

$$
\max \frac{wS_b w^\intercal}{wS_ww^\intercal} \\
w S_w w^\intercal = 1
$$

#### Solution

$w$ is the eigenvector of the matrix $S\_w^-1 S\_b$

m - 1 eigenvectors associated with highest eigenvalues are used to discriminate between m classes.

## Classification

### Centroid Based Linear Discriminant Classifier

#### Two class case

$$
\theta = w \cdot \frac{1}{2}(\mu_1+\mu_2)
$$

Predict 1 if $wx &lt; \theta$

#### Multiclass case

Centres

$$
c_i = \frac{1}{n_i} \sum_{x \in X_i} W^\intercal x
$$

Assign the class of test data x by

$$
\arg\min_i ||c_i - W^T x||
$$

## Not proved

### Covariance matrix

$$
\begin{aligned}
C_X &= (X-E_0(\mu))^\intercal(X-E_0(\mu)) \\
&=X^\intercal X - n\mu \mu^T
\end{aligned}
$$

The eigenvectors for $S\_w^-1S\_b$ and $C\_X^-1 S\_b$ are the same.

## References

R. Fisher \(1936\). ‘The use of multiple measurements in taxonomic problems’. Annals of Eugenics \(7\):179–188.

R. A. Johnson & D. W. Wichern \(1988\). Applied Multivariate Statistical Analysis. Prentice Hall.  


