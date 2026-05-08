---
tags:
  - MATH283
---
Suppose that $f(x, y)$ is a differentiable real function of two variables whose second [[Partial derivation|Partial derivatives]] exist and are continuous. The [[Hessian matrix]] $H$ of $f$ is the $2 \times 2$ matrix of partial derivatives of $f$:
$$H(x, y) = \begin{bmatrix} f_{xx}(x, y) & f_{xy}(x, y) \\ f_{yx}(x, y) & f_{yy}(x, y) \end{bmatrix}$$

Define $D(x, y)$ to be the determinant
$$D(x, y) = \det{ (H(x, y)) } = f_{xx}(x, y)f_{yy}(x, y) - (f_{xy}(x, y))^2$$

of $H$. Finally, suppose that $(a, b)$ is a critical point of $f$, that is, that $f_x(a, b) = f_y(a, b) = 0$. Then the second partial derivative test asserts the following:
1. If $D(a, b) > 0$ and $f_{xx}(a, b) > 0$ then $(a, b)$ is a local minimum of $f$.
2. If $D(a, b) > 0$ and $f_{xx}(a, b) < 0$ then $(a, b)$ is a local maximum of $f$.
3. If $D(a, b) < 0$ then $(a, b)$ is saddle point of $f$.
4. If $D(a, b) = 0$ then the second partial derivative test is inconclusive.