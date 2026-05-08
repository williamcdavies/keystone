---
tags:
  - MATH181
---
Linearisation is an effective method for approximating the output of a function $y = f(x)$ at any $x = a$ based on the value and slope of the function at $x = b$, given that $f(x)$ is differentiable on $[a,b]$ (or $[b,a]$) and that $a$ is reasonably close to $b$. 

The equation for a linearised function at $x = a$ can be abstracted to: 
$$L_a(x) = f(a) + f'(a)(x - a)$$

```
Approximate sqrt(4.001):
```

> [!example]
> $$\begin{align}
f(a) &= \sqrt{a} \\\\
f'(a) &= \frac{1}{2 \sqrt{a} } \\\\
L_a(x) &= \sqrt{a} + \frac{1}{2 \sqrt{a} \times (x - a)} \\\\
L_a(x) &= \sqrt{4} + \frac{1}{2 \sqrt{4} \times (x - 4)} \\\\
L_a(x) &= 2 + \frac{x - 4}{4} \\\\
L_a(x) &= 2 + \frac{4.001 - 4}{4} \\\\
L_a(x) &= 2.00025
\end{align}$$

## Linearisation of Multivariable Functions
Given a function $z = f(x, y)$ with continuous [[Partial derivation|Partial derivatives]] that exist at the point $(x_0, y_0)$, the linear approximation of $f$ at the point $(x_0, y_0)$ is given by the equation
$$L(x, y) = f(x_0, y_0) + f_x(x_0, y_0)(x - x_0) + f_y(x_0, y_0)(y - y_0)$$


