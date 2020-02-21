# Limited-memory BFGS

## Broyden–Fletcher–Goldfarb–Shanno algorithm \(BFGS\)

Problem: minimizing an unconstrained function $$f$$of $$n$$variables

Let $$f$$ be the function to be minimized, $$g$$ its gradient and $$h$$ its hessian

Define $$s_k = x_{k+1} - x_k$$ and $$y_k = g_{k+1} - g_k$$

The BFGS update is given by

$$
\bar{H} = H + \frac{ss^T}{y^Ts}[\frac{y^THy}{y^Ts}+1]-\frac{1}{y^Ts}[sy^TH+Hys^T]
$$

Let

$$
U(s,y,H) = \frac{ss^T}{y^Ts}[\frac{y^THy}{y^Ts}+1]-\frac{1}{y^Ts}[sy^TH+Hys^T]
$$

#### Then the sum form can be written as

$$
\bar{H} = H + U(s,y,H)
$$

The formula can also be written in product form

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

#### Then the product form can be written as

$$
\bar{H}=v^THv+\rho ss^T
$$

## Limited-memory BFGS

The idea is to drop old correction $$s$$, instead of storing all the corrections to restore the exact Hessian matrix $$H$$, we just store the latest $$m$$corrections.

So for any $$k>m$$, let $$s=k+1-m$$, then $$H_{k+1}$$is given by

$$
\begin{cases}
\hat{H}_s = H_0\\
\text{For } j = s, s+1, ...,k, \;\hat{H}_{j+1}=\hat{H}_j+U(s_j,y_j,\hat{H}_j)\\
H_{k+1}=\hat{H}_{k+1}
\end{cases}
$$

{% hint style="info" %}
$$H_0$$is diagonal.
{% endhint %}

## References

1. J. Nocedal, "Updating Quasi-Newton Matrices with Limited Storage," Mathematics of Computation, vol. 35, no. 151, pp. 773-782, 1980, doi: 10.2307/2006193.

