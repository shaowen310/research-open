# Linear Algebra

## Vector product

### Element-wise product

$$
\boldsymbol{u}*\boldsymbol{v}=\begin{bmatrix} u_1v_1 & u_2v_2 & \dots & u_n v_n \end{bmatrix}
$$

### Inner product

$$
\mathbf{u} \cdot \mathbf{v} = \mathbf{u}^\intercal \mathbf{v}
$$

### Outer product

Let vector $$\mathbf{u}=(u_1, u_2, ..., u_m)$$, $$\mathbf{v}=(v_1, v_2, ..., v_n)$$

Then

$$
\boldsymbol{u} \otimes \boldsymbol{v} = \boldsymbol{u} \boldsymbol{v}^\intercal= E_0(\boldsymbol{u})*E_1(\boldsymbol{v}) = \begin{bmatrix}      u_1 v_1 & u_1 v_2& \dots \\     \vdots & \ddots & \\     u_m v_1 &        & u_m v_n      \end{bmatrix}
$$

## Matrix product

### Product of ordinary matrices

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

### Multiplying a diagonal matrix

Let a diagonal matrix

$$
D = \begin{bmatrix}\lambda_1 & & & \\& \lambda_2 & & \\& & \ddots & \\ & & & \lambda_n \end{bmatrix}
$$

Then

Column-wise view

$$
AD = \begin{bmatrix}\lambda_1 \mathbf{c}_1 & \lambda_2 \mathbf{c}_2 & \dots & \lambda_n \mathbf{c}_n\end{bmatrix}
$$

Row-wise view

$$
DA = \begin{bmatrix}\lambda_1\mathbf{r}_1\\\lambda_2\mathbf{r}_2\\\vdots\\\lambda_n\mathbf{r}_n\end{bmatrix}
$$

## Eigenvalue and eigenvector

$$
A\bm{v}=\lambda\bm{v}
$$

Then λ is an eigenvalue of A, and $\bm{v}$ is an eigenvector of A. λ is the corresponding eigenvalue of the eigenvector $\bm{v}$.

## Diagonalisation

$$
P^\intercal D P = A
$$

Then

$$
P^\intercal D = A P^\intercal
$$

Consider the eigenvalues and eigenvectors of A

$$
P^\intercal=\begin{bmatrix}\bm{v}_1 & \bm{v}_2 & \dots\end{bmatrix}
$$

Then

$$
\begin{bmatrix}\lambda_1\bm{v}_1 & \lambda_2\bm{v}_2 &\dots\end{bmatrix} = \begin{bmatrix}A\bm{v}_1 & A\bm{v}_2 & \dots\end{bmatrix}
$$

