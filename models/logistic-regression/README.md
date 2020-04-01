# Logistic Regression

It is used for binary classification. For data with more than 2 classes, [Softmax Regression](softmax-regression.md) has to be used.

## Model

The output of the model is the estimated probability.

$$
h(x) = \text{sigmoid}(wx+b)
$$

### Sigmoid function

$$
\text{sigmoid}(z) = \frac{1}{1+e^{-z}}
$$

### Decision boundary

Let $$p$$ be the threshold, then predict 1 when $$h(x) \geq p$$ , and predict 0 when $$h(x) < p$$ .

## Training Objective

### Loss function

#### Cross-entropy loss

$$
\begin{cases}
  L(h(x),y) = -log(h(x)) & \text{if }y=1\\
  L(h(x),y) = -log(1-h(x)) & \text{if }y=0
\end{cases}
$$

For empirical risk minimization and regularization, see [Linear Regression](../linear-regression/) for details.

#### Summary

$$
J(h,x,y) = \frac{1}{n}\sum_{i=1}^{n}(y_i log(h(x_i)) + (1-y_i)log(1-h(x_i)))+\lambda R(h)
$$

If $$y \in \{1, -1\}$$ , then the loss function is

$$
J(w,b,x,y) = \frac{1}{n}\sum_{i=1}^n(1+e^{-y_i(wx_i+b)}) + \lambda R(w)
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

#### Gradient

Note: regularization term is omitted

$$
\frac{\partial J}{\partial w} = \frac{1}{n}\sum_{i=1}^n(h(x_i)-y_i)x_i
$$

If $$y \in \{1, -1\}$$ , then the gradient is

$$
\frac{\partial J}{\partial w} = \frac{1}{n}\sum_{i=1}^{n}(\frac{1}{1+e^{-y_i(wx_i+b)}}-1)y_ix_i
$$

Proof see [http://thegrandjanitor.com/2015/08/20/gradient-descent-for-logistic-regression/](http://thegrandjanitor.com/2015/08/20/gradient-descent-for-logistic-regression/)

