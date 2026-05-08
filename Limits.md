---
tags:
  - MATH283
aliases:
  - Limit
---
The limit of a function is defined as $L$, where $f$ tends to $L$ as its independent variables tend to some number $p$.

## The Limit of Single-variable Functions
Suppose $f : \mathbb{R} \rightarrow \mathbb{R}$ is a function defined on the real line, and there are two real numbers $p$ and $L$. One would say that the limit of $f$, as $x$ approaches $p$, is $L$ and written
$$\lim_{x \rightarrow p}{f(x)} = L$$

## The Limit of Multi-variable Functions
The definition of a limit can be extended to functions of more than one variable. In the case of a function $f : S \times T \rightarrow \mathbb{R}$ defined on $S \times T \subseteq \mathbb{R}^2$, we defined the limit as follows: the limit of $f$ as $(x, y)$ approaches $(p, q)$ is $L$, written
$$\lim_{(x, y) \rightarrow (p, q)}{f(x, y)} = L$$

If a function $f$ is continuous over $(p, q)$, then the limit as $(x, y)$ approaches $(p, q)$ is $f(p, q)$.

Unlike taking the limit of single-variable functions, the limit of multi-variable functions may be taken along an infinite number of unique paths. These paths make it possible to arrive at differing limiting values when approaching $(x_0, y_0)$. If more than one limiting value is found, then the $\lim_{(x, y) \rightarrow (p, q)}{f(x, y)}$ does not exist (this is analogous to the left and right hand limits of single variable functions not being equal).

```
Show \lim_{(x, y) \rightarrow (0, 0)}{ \frac{3xy}{x^2 + y^2} } does not exist by finding the limits along the lines y = mx.
```

> [!example]
Evaluating $\lim_{(x, y) \rightarrow (0, 0)}{ \frac{3xy}{x^2 + y^2} }$ along the lines $y = mx$ means replace all $y$'s with $mx$ and evaluating the resulting limit:
> $$\begin{align}
\lim_{(x, mx) \rightarrow (0, 0)}{ \frac{3x(mx)}{x^2 + (mx)^2} } &= \lim_0{ \frac{3mx^2}{x^2(m^2 + 1)} } \\\\
&= \lim_0{ \frac{3m}{m^2 + 1} } \\\\
&= \frac{3m}{m^2 + 1}
\end{align}$$
>
While the limit exists for each choice of $m$, we get a different limit for each choice of $m$. That is, along different lines we get differing values, meaning the limit does not exist.