# Logistic Regression

The output of the model is the estimated probability.

It is used for binary classification. For data with more than 2 classes, softmax regression has to be used.

## Model

$$
h(x) = \text{sigmoid}(wx+b)
$$

### Sigmoid function

$$
\text{sigmoid}(t) = \frac{1}{1+e^{-t}}
$$

## Training Objective

### Loss function

Ideas: Empirical risk minimization and regularization. See [Linear Regression](../linear-regression/) for details.

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

## Solver

### Convex programming

1. **Gradient descent** and its family including **Stochastic Gradient Descent \(SGD\)**
2. **Newton's method** and its family

### Gradient descent



