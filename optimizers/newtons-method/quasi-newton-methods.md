# Quasi-Newton Methods

## Broyden–Fletcher–Goldfarb–Shanno algorithm \(BFGS\)

Problem: minimizing an unconstrained function $$f$$of $$n$$variables

Let $$f$$ be the function to be minimized, $$g$$ its gradient and $$h$$ its hessian

Define $$s_k = x_{k+1} - x_k$$ and $$y_k = g_{k+1} - g_k$$

#### The BFGS update is given by

$$
\bar{H} = H + \frac{ss^T}{y^Ts}[\frac{y^THy}{y^Ts}+1]-\frac{1}{y^Ts}[sy^TH+Hys^T]
$$

#### The formula can also be written in product form

$$
\bar{H}=(I-\rho sy^T)H(I-\rho y s^T)+\rho ss^T
$$

where $$\rho = \frac{1}{y^Ts}$$

{% hint style="info" %}
Verification

The key is to verify

$$
\rho^2 ss^Ty^THy=\rho^2 sy^THys^T
$$

Note that $$y^THy$$is a scalar.
{% endhint %}

Let $$v = (I-\rho ys^T)$$

Then [the product form](quasi-newton-methods.md#the-formula-can-also-be-written-in-product-form) can be written as

$$
\bar{H}=v^THv+\rho ss^T
$$

### Limited-memory BFGS

The BFGS 

## References

1. J. Nocedal, "Updating Quasi-Newton Matrices with Limited Storage," Mathematics of Computation, vol. 35, no. 151, pp. 773-782, 1980, doi: 10.2307/2006193.

