---
tags:
  - MATH283
---
A directional derivative measures the rate at which a function changes in a particular direction at a given point.

If $f$ is a differentiable function of $x_0$ and $y_0$, then $f$ has a directional derivative in the direction of any unit vector $\vec{u} = \langle a, b \rangle$ and 
$$D_u f(x_0, y_0) = f_{x_0}(x_0, y_0)a + f_{y_0}(x_0, y_0)b$$

The directional derivative $D_u$ of a differentiable function $f(x, y)$ can be written as the [[Dot products|Dot product]] of the unit vector $\vec{u}$ and the gradient $\nabla f(x, y)$
$$\begin{align}
D_u f(x, y) &= f_x(x, y,)a + f_y(x, y)b \\\\
&= \langle f_x(x, y), f_y(x, y) \rangle \cdot \langle a, b \rangle \\\\
&= \langle f_x(x, y), f_y(x, y) \rangle \cdot \vec{u}
\end{align}$$

## Maximum Rate of Change
The maximum rate of change for some directional derivative $D_u f(x, y)$ is the instantaneous change at some point $P$ in the direction of $\text{ || } \nabla f(x, y) \text{ || }$.

## Minimum Rate of Change
The maximum rate of change for some directional derivative $D_u f(x, y)$ is the instantaneous change at some point $P$ in the direction of $-\text{ || } \nabla f(x, y) \text{ || }$.