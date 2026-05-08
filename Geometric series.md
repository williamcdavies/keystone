---
tags:
  - MATH182
---
A geometric series is a class of [[Series]] whose value is determined as the sum of $n$ terms which follow the geometric model $ar^n$ where $a$ is some constant and $r$ is the common ratio.

The infinite sum of a geometric series can be calculated as $\frac{a}{1 - r}$, where $a$ is the initial term and $r$ is the common ratio, as described by the summation models: $\sum^{ \infty }_{n = 1}{ar^{n-1}}$ and $\sum^{ \infty }_{n = 0}{ar^{n}}$.

```
Find the sum of the series if it converges.
```

> [!example]
> $$\begin{align}
\sum^{ \infty }_{n = 1}{ 0.2^{n - 1} } &= \sum^{ \infty }_{n = 1}{ \left( \frac{1}{5} \right)^{n - 1} } \\\\
&= 1 + \frac{1}{5} + \frac{1}{25} + \frac{1}{125} + \dots + 0 \\\\
&= \frac{1}{1 - \frac{1}{5} } \\\\
&= \frac{1}{ \frac{4}{5} } \\\\
&= \frac{5}{4}
\end{align}$$

```
Find the sum of the series if it converges.
```

> [!example]
> $$\begin{align}
\sum^{ \infty }_{n = 1}{ \frac{9}{(-2)^n} } &= \sum^{ \infty }_{n = 1}{ \frac{ -\frac{9}{2} }{(-2)^{n - 1}} } \\\\
&= \sum^{ \infty }_{n = 1}{ -\frac{9}{2} \left( \frac{1}{-2} \right)^{n -1} } \\\\
&= -\frac{9}{2} + \frac{9}{4} - \frac{9}{8} + \frac{9}{16} - \dots + 0 \\\\
&= \frac{ -\frac{9}{2} }{1 + \frac{1}{2} } \\\\
&= \frac{ -\frac{9}{2} }{ \frac{3}{2} } \\\\
&= \frac{-18}{6} \\\\
&= -3
\end{align}$$