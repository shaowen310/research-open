# Linear Regression

## Model

$$
h(x) = wx+b
$$

## Training objective

### Loss function

#### Square error

$$
L(h(x_i),y_i) = ||y_i-h(x_i)||^2
$$

#### Empirical risk minimisation

$$
R_\text{emp}(h)=\frac{1}{n}\sum_{i=1}^{n}L(h(x_i),y_i)
$$

Choose the $$\hat{h}$$ which minimises the empirical risk

$$
\hat{h} = \underset{h \in \mathcal{H}}{\arg\min}R_{\text{emp}}(h)
$$

#### Regularisation term

L2 regularisation

$$
R(h)=||w||^2
$$

#### Summary

Loss function is defined as

$$
J(h,x,y) = \frac{1}{n}\sum_{i=1}^{n}||h(x_i)-y_i||^2+\lambda R(h)
$$

### Objective

The objective is to find the $$\hat{h}$$ which minimises the loss function

$$
\hat{h} = \underset{h \in \mathcal{H}}{\arg\min}J(h,x,y)
$$

### Hyper parameters

$$\lambda$$ is used to adjust the strength of regularisation.

## Solver

### Convex programming

1. **Gradient descent** and its family
2. **Newton's method** and its family

