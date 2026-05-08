---
tags:
  - MATH283
---
Let $S$ be a surface defined by a differentiable function $z = f(x, y)$, and let $P_0 = (x_0, y_0)$ be a point in the domain of $f$. Then, the equation of the tangent plane to $S$ at $P_0$ is given by
$$z = f(x_0, y_0) + f_x(x_0, y_0)(x - x_0) + f_y(x_0, y_0)(y - y_0)$$

```
Find equations of the following.

2(x - 1)^2 + (y - 3)^2 + (z - 1)^2 = 10, (2, 5, 3)
```

```
(a) The tangent plane.
```

> [!example]
The tangent plane to the surface given by $f(x, y, z) = k$ at $(x_0, y_0, z_0)$ has the equation,
> $$f_x(x_0, y_0, z_0)(x - x_0) + f_y(x_0, y_0, z_0)(y - y_0) + f_z(x_0, y_0, z_0)(z - z_0) = 0$$
> 
where $f(x, y, z)$ can be defined as $f(x, y) - z = 0$.
>
> $$f_x(2, 5, 3) = \frac{ \partial }{ \partial x} f(2, 5, 2) = 4(x - 1) = 4(2 - 1) = 4$$
> $$f_y(2, 5, 3) = \frac{ \partial }{ \partial y} f(2, 5, 2) = 2(y - 3) = 2(5 - 3) = 4$$
> $$f_z(2, 5, 3) = \frac{ \partial }{ \partial z} f(2, 5, 2) = 2(z - 1) = 2(3 - 1) = 4$$
>
The equation of the tangent plane is then,
> $$f_x(2, 5, 3)(x - 2) + f_y(2, 5, 3)(y - 5) + f_z(2, 5, 3)(z - 3) = 4(x - 2) + 4(y -  5) + 4(z - 3) = 0$$

```
(b) The normal line.
```

> [!example]
The normal line to the surface given by $f_(x, y, z) = k$ at $(x_0, y_0, z_0)$ has the equation'
> $$\vec{r} (t) = \langle x_0, y_0, z_0 \rangle + t \nabla f(x_0, y_0, z_0)$$
> 
where $f(x, y, z)$ can be defined as $f(x, y) - z = 0$.
>
$\nabla f(2, 5, 3) = \langle f_x(2, 5, 3), f_y(2, 5, 3), f_z(2, 5, 3) \rangle = \langle 4(2 - 1), 2(5 -3), 2(3 - 1) \rangle = \langle 4, 4, 4 \rangle$
>
The equation of the normal line is then,
$$\vec{r} (t) = \langle 2, 5, 3 \rangle + t \langle 4, 4, 4 \rangle = \langle 2 + 4t, 5 + 4t, 3 + 4t \rangle$$