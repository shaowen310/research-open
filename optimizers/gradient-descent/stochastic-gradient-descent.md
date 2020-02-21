# Stochastic Gradient Descent

## The optimization problem

#### Minimising an objective function that has an form of a sum

$$
Q(w)=\frac{1}{n}\sum_{i=1}^{n}Q_i(w)
$$

where $$Q_i$$ is typically associated with the $$i$$-th observation in the training dataset.

## Stochastic gradient descent

### Batch gradient descent

To minimize the [objective function](stochastic-gradient-descent.md#minimising-an-objective-function-that-has-an-form-of-a-sum), update $$w$$

$$
w:=w-\eta \nabla Q(w)=w-\eta \cdot \frac{1}{n} \sum_{i=1}^{n}\nabla Q_i(w)
$$

### Stochastic gradient descent

Instead using the average of all $$\nabla Q_i$$, we just pick one at random

$$
w:=w-\eta \nabla Q_i(w)
$$

The idea is based on

$$
\underset{i}{\mathbb{E}}[\nabla Q_i(w)] = \nabla Q(w)
$$

if $$i$$is picked uniformly at random

