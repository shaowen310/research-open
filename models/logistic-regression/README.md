---
description: Model and Training Objective and Solver parts are verified on 1/4/2020.
---

# Logistic Regression

It is used for binary classification. For data with more than 2 classes, [Softmax Regression](softmax-regression.md) has to be used.

## Model

The output of the model is the estimated probability.

$$
h(x) = S(f(x))
$$

### Linear term

$$
f(x) = wx+b
$$

### Sigmoid function

$$
S(z) = \frac{1}{1+e^{-z}}
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

For empirical risk minimisation and regularisation, see [Linear Regression](../linear-regression/) for details.

#### Summary

$$
J(h,x,y) = -\frac{1}{n}\sum_{i=1}^{n}(y_i log(h(x_i)) + (1-y_i)log(1-h(x_i)))+\lambda R(h)
$$

If $$y \in \{1, -1\}$$ , then the loss function is

$$
J(w,b,x,y) = \frac{1}{n}\sum_{i=1}^n log(1+e^{-y_i (wx_i + b)}) + \lambda R(w)
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

### Gradient descent

#### Gradient

Note: regularisation term is omitted

$$
\frac{\partial J}{\partial w} = \frac{1}{n}\sum_{i=1}^n(h(x_i)-y_i)x_i
$$

If $$y \in \{1, -1\}$$ , then the gradient is

$$
\frac{\partial J}{\partial w} = \frac{1}{n}\sum_{i=1}^{n}(h(y_i x_i)-1)y_ix_i
$$

Proof see [http://thegrandjanitor.com/2015/08/20/gradient-descent-for-logistic-regression/](http://thegrandjanitor.com/2015/08/20/gradient-descent-for-logistic-regression/)

## Vertically Partitioned Data

We consider two parties' case, and omit the regularisation term for simplicity.

Assume $$y \in \{1, -1\}$$

Let $$u_i = w_A x_i^A + w_B x_i^B + b$$

### Loss function

$$
J(w,b,x,y) = \frac{1}{n}\sum_{i=1}^n log(1+e^{-y_i u_i})
$$

### Gradient

$$
\frac{\partial J}{\partial w_A} = \frac{1}{n}\sum_{i=1}^{n}(S(y_i u_i)-1)y_ix_i^A
$$

$$
\frac{\partial J}{\partial w_B} = \frac{1}{n}\sum_{i=1}^{n}(S(y_i u_i)-1)y_ix_i^B
$$

$$
\frac{\partial J}{\partial b} = \frac{1}{n}\sum_{i=1}^{n}(S(y_i u_i)-1)y_i
$$

## Logistic Regression and Neural Networks

Logistic regression can be regarded as one layer in neural networks.

Sigmoid function is seldom used as nonlinear activation function because:

1. Vanishing gradient problem.
2. Its output isn’t zero centred. It makes the gradient updates move along certain directions and therefore makes optimisation harder**.**

Hyperbolic Tangent function - $$ tanh(x) = \frac{1 - e^{-2x}}{1 + e^{-2x}}$$ 

Its output is zero centred, and it is preferred over Sigmoid function in practice. However, it still suffers from vanishing gradient problem.

## References

1. [towards data science: Activation functions and it’s types-Which is better?](https://towardsdatascience.com/activation-functions-and-its-types-which-is-better-a9a5310cc8f)

