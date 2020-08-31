# Softmax Regression

## Model

The output of the model is the estimated probabilities of x being classified as each class.

$$
h(\mathbf{x}) = \sigma(f(\mathbf{x}))
$$

Softmax function **σ**: $\mathbb{R}^k \rightarrow \mathbb{R}^k$ is defined as

$$
\theta(\mathbf{x})_i =\frac{\exp(x_i)}{\sum_j \exp(x_j)}
$$

Linear transform f: $mathbb{R}^m \rightarrow \mathbb{R}^k$ is defined as

$$
f(\mathbf{x})=\mathbf{W}\mathbf{x} + \mathbf{b}
$$



