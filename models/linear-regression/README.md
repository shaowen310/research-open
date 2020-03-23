# Linear Regression

## Model

$$
h(x) = wx+b
$$

## Training

### Loss function

#### Least squares

$$
\sum_{i=1}^{n}||y_i-h(x_i)||^2
$$

#### Empirical risk minimization

$$
R_\text{emp}(h)=\frac{1}{n}\sum_{i=1}^{n}L(h(x_i),y_i)
$$

Choose the $$\hat{h}$$ which minimizes the empirical risk

$$
\hat{h} = \underset{h \in \mathcal{H}}{\arg\min}R_{\text{emp}}(h)
$$

#### Regularization term

$$
R(h)=||w||^2
$$

#### Summary

Loss function is defined as

$$
J(h,x,y) = \frac{1}{n}\sum_{i=1}^{n}||h(x_i)-y_i||^2+\lambda R(h)
$$

### Objective

The objective is to find the $$\hat{h}$$ which minimizes the loss function

$$
\hat{h} = \underset{h \in \mathcal{H}}{\arg\min}J(h,x,y)
$$

### Hyper parameters

One hyper parameter is introduced by the regularization term: $$\lambda$$

### Solver

#### Convex programming

1. **Gradient descent** and its family including **Stochastic Gradient Descent \(SGD\)**
2. **Newton's method** and its family

