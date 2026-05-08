---
tags:
  - MATH182
---
[[Series|Infinite series]] are said to converge conditionally if they converge but lack [[Absolute convergence]]. The [[Ratio test]] can be used to determine if an infinite series is conditionally convergent:

```
Find the radius of convergence of the series.
```

> [!example]
> $$\begin{align}
&\sum^{ \infty }_{n = 1}{ (-6)^n \cdot \frac{x^n}{n^{ \frac{1}{3} } } } \\\\
&\sum^{ \infty }_{n = 1}{ (-1)^n \cdot \frac{6^n x^n}{n^{ \frac{1}{3} } } } \\\\
\text{ | } a_n \text{ | } &= \frac{6^n x^n}{n^{ \frac{1}{3} } } \\\\
L &= \lim_{n \to \infty }{ \frac{a_{n + 1}}{a^n} } \\\\
L &= \lim_{n \to \infty }{ \frac{6^{n + 1} x^{n + 1}}{(n + 1)^{ \frac{1}{3} } } \cdot \frac{n^{ \frac{1}{3} } }{6^n x^n} } \\\\
L &= \lim_{n \to \infty }{ \frac{6x \cdot n^{ \frac{1}{3} }}{(n+1)^{ \frac{1}{3} }} } \\\\
L &= 6x \cdot \lim_{n \to \infty }{ \frac{n^{ \frac{1}{3} }}{(n+1)^{ \frac{1}{3} }} } \\\\
L &= 6x \cdot 1 \\\\
L &= 6x \\\\
&\cdots \\\\
L &< 1 \\\\
6x &< 1 \\\\
x &< \frac{1}{6} \\\\
R &= \frac{1}{6}
\end{align}$$