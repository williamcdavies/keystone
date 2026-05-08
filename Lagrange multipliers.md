---
tags:
  - MATH283
---
The method of Lagrange multipliers is a strategy for finding the local maxima and minima of a function subject to equation constraints.

The basic idea is to convert a constrained problem into a form such that the derivative test of an unconstrained problem can still be applied. The relationship between the gradient of the function and gradients of the constraints rather naturally leads to a reformulation of the original problem, known as the Lagrangian function. In the general case, the Lagrangian is defined as
$$\mathcal{L} (x, \lambda ) \equiv f(x) + \langle \lambda , g(x) \rangle$$

For functions $f$, $g$, $\lambda$ is called the Lagrange multiplier.

In simple cases, where the inner product is defined as the [[Dot products|Dot product]], the Lagrangian is
$$\mathcal{L} (x, \lambda ) \equiv f(x) + \lambda \cdot g(x)$$

The method can be summarised as follows: in order to find the maximum or minimum of a function $f$ subject to the equality constraint $g(x) = 0$, find the stationary points $\mathcal{L}$ considered as a function of $x$ and the Lagrange multiplier $\lambda$. This means that all [[Partial derivation|Partial derivatives]] should be zero, including the partial derivative with respect to $\lambda$.
$$\frac{ \partial \mathcal{L} }{ \partial x} = 0 \qquad \frac{ \partial \mathcal{L} }{ \partial \lambda } = 0$$

or equivalently
$$\frac{ \partial f(x)}{ \partial x} + \lambda \cdot \frac{ \partial g(x)}{ \partial x} = 0 \qquad g(x) = 0$$

The solution corresponding to the original constrained optimisation is always a saddle point of the Lagrangian function, which can be identified among the stationary points from the definiteness of the bordered [[Hessian matrix]].

```
Find the minimum value of f(x, y) = x^2 + 4y^2 - 2x + 8y subject to the constraint x + 2y = 7.
```

> [!example]
The objective function is $f(x, y) = x^2 + 4y^2 - 2x + 8y$. To determine the constraint function, we must first subtract $7$ from both sides of the constraint. This gives $x + 2y - 7 = 0$. The constraint function is equal to the left-hand side, so $g(x, y) = x + 2y - 7$. The problem asks us to solve for the minimum value of $f$, subject to the constraint.
>
We then must calculate the gradients of both $f$ and $g$:
> $$\begin{align}
\nabla f(x, y) &= \langle 2x - 2, 8y + 8 \rangle \\\\
\nabla g(x, y) &= \langle 1, 2 \rangle
\end{align}$$
>
The equation $\nabla f(x_0, y_0) = \lambda \nabla g(x_0, y_0)$ becomes 
> $$\langle 2x_0 - 2, 8y_0 + 8 \rangle = \lambda \langle 1, 2 \rangle$$
> 
which can be rewritten as
> $$\langle 2x_0 - 2, 8y_0 + 8 \rangle = \langle \lambda , 2 \lambda \rangle$$
> 
Next, we set the coefficients of $\widehat{i}$ and $\widehat{j}$ equal to each other:
> $$\begin{align}
2x_0 - 2 &= \lambda \\ \lambda \\
8y_0 + 8 = 2 \lambda 
\end{align}$$
>
The equation $g(x_0, y_0) = 0$ becomes $x_0 + 2y_0 - 7 = 0$. Therefore, the system of equations the needs to be solved is
> $$\begin{align}
2x_0 - 2 &= \lambda \\\\
8y_0 + 8 &= 2 \lambda \\\\
x_0 + 2y_0 - 7 &= 0
\end{align}$$
>
This is a linear system of three equations in three variables. We start by solving the second equation for $\lambda$ and substituting it into the first equation. This gives $\lambda = 4y_0 + 4$, so substituting this into the first equation gives
> $$2x_0 - 2= 4y_0 + 4$$
>
Solving this equation for $x_0$ gives $x_0 = 2y_0 + 3$. We then substitute this into the third equation:
> $$\begin{align}
(2y_0 + 3) + 2y_0 - 7 &= 0 \\\\
4y_0 - 4 &= 0 \\\\
y_0 &= 1
\end{align}$$
>
Since $x_0 = 2y_0 + 3$, this gives $x_0 = 5$.
>
Next, we evaluate $f(x, y) = x^2 + 4y^2 - 2x + 8y$ at the point $(5, 1)$,
> $$f(5, 1) = 5^2 + 4(1)^2 - 2(5) + 8(1) = 27$$
>
To ensure this corresponds to a minimum value on the constraint function, let's try some other point son the constraint from either side of the point $(5, 1)$, such as the intercepts of $g(x, y) = 0$ which are $(7, 0)$ and $(0, 3.5)$.
>
We get $f(7, 0) = 35 > 27$ and $f(0, 3.5) = 77 > 27$.
>
So it appears that $f$ has a relative minimum of $27$ at $(5, 1)$, subject to the given constraint.