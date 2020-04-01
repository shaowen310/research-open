# Support Vector Machines

## Model

It is also known as maximum-margin \(linear\) classifier.

$$
\begin{cases}
  h(x) = 1 & \text{if } wx+b \geq 0\\
  h(x) = -1 & \text{if } wx+b < 0
\end{cases}
$$

## Training Objective

### Loss function

Suppose $$y \in \{1, -1\}$$

Use soft-margin for non-linearly separable data

$$
J(w,b,x,y) = \frac{1}{n}\sum_{i=1}^n \max(0, 1-y_i(wx_i+b)) + \lambda ||w||^2
$$

{% hint style="info" %}
Normal vector of a plane

For plane $$wx+b=0$$ , $$w$$ is the normal vector of the plane.

Geometric definition of dot product

$$
a \cdot b = ||a||||b||cos \theta
$$

Projection of one vector to the other vector

$$
||a||cos \theta = \frac{a \cdot b}{||b||}
$$

Let there be a plane that all positive samples satisfies

$$
wx+b \geq 1
$$

Another plane that all negative samples satisfies

$$
wx+b \leq -1
$$

The margin between plane $$wx+b=1$$ and $$wx+b=-1$$ is $$2/||w||$$ 

To maximise the margin, we need to minimise$$||w||$$ 
{% endhint %}

### Objective

The objective is to find $$\hat{w}$$ and $$\hat{b}$$ which minimises the loss function

$$
\hat{w}, \hat{b} = \underset{w,b}{\arg\min}J(w,b,x,y)
$$

### Hyper parameters

$$\lambda$$ is used to adjust the relative penalty introduced by non-linearly separable points.

## Solver

### Convex programming

1. **Gradient descent** and its family
2. **Newton's method** and its family



