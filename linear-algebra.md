# Linear Algebra

## Inner product

$$
\mathbf{u} \cdot \mathbf{v} = \mathbf{u}^\intercal \mathbf{v}
$$

## Outer product

Let vector $$\mathbf{u}=(u_1, u_2, ..., u_m)$$, $$\mathbf{v}=(v_1, v_2,  ..., v_n)$$

Then

$$
\mathbf{u} \otimes \mathbf{v} = \mathbf{u} \mathbf{v}^\intercal= \begin{bmatrix}      u_1 v_1 & u_1 v_2& \dots \\     \vdots & \ddots & \\     u_m v_1 &        & u_m v_n      \end{bmatrix}
$$

## Matrix product

Let matrix 

$$
A = \begin{bmatrix} \mathbf{r}_1^\intercal \\ \mathbf{r}_2^\intercal \\ \vdots \\ \mathbf{r}_m^\intercal  \end{bmatrix} = \begin{bmatrix} \mathbf{c}_1 & \mathbf{c}_2 & \dots & \mathbf{c}_n \end{bmatrix}
$$

Then

Element-wise view

$$
A^\intercal A = \begin{bmatrix} \mathbf{c}_1^\intercal \\ \mathbf{c}_2^\intercal \\ \vdots \\ \mathbf{c}_n^\intercal \end{bmatrix} \cdot \begin{bmatrix} \mathbf{c}_1 & \mathbf{c}_2 & \dots & \mathbf{c}_n \end{bmatrix} = \begin{bmatrix} \mathbf{c}_1^\intercal \mathbf{c}_1 & \mathbf{c}_1^\intercal \mathbf{c}_2& \dots \\ \vdots & \ddots & \\ \mathbf{c}_n^\intercal \mathbf{c}_1 & & \mathbf{c}_n^\intercal \mathbf{c}_n \end{bmatrix}
$$

$$
A A^\intercal  = \begin{bmatrix} \mathbf{r}_1^\intercal \\ \mathbf{r}_2^\intercal \\ \vdots \\ \mathbf{r}_m^\intercal \end{bmatrix} \cdot \begin{bmatrix} \mathbf{r}_1 & \mathbf{r}_2 & \dots & \mathbf{r}_n \end{bmatrix} = \begin{bmatrix} \mathbf{r}_1^\intercal \mathbf{r}_1 & \mathbf{r}_1^\intercal \mathbf{r}_2& \dots \\ \vdots & \ddots & \\ \mathbf{r}_m^\intercal \mathbf{r}_1 & & \mathbf{r}_m^\intercal \mathbf{r}_m \end{bmatrix}
$$

Column-wise view

$$
A^\intercal A = A^\intercal \cdot \begin{bmatrix} \mathbf{c}_1 & \mathbf{c}_2 & \dots & \mathbf{c}_n \end{bmatrix} = \begin{bmatrix} A^\intercal\mathbf{c}_1 & A^\intercal\mathbf{c}_2 & \dots & A^\intercal\mathbf{c}_n \end{bmatrix}
$$

Row-wise view

$$
A^\intercal A = \begin{bmatrix} \mathbf{c}_1^\intercal \\ \mathbf{c}_2^\intercal \\ \vdots \\ \mathbf{c}_n^\intercal \end{bmatrix} \cdot A = \begin{bmatrix} \mathbf{c}_1^\intercal A \\ \mathbf{c}_2^\intercal A \\ \vdots \\ \mathbf{c}_n^\intercal A\end{bmatrix}
$$
