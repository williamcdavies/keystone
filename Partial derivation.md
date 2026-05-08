---
tags:
  - MATH283
aliases:
  - Partial derivatives
---
The partial derivative of a function of several variables is its derivative with respect to one of those variables, with the others held constant.

Like ordinary derivatives, the partial derivative is defined by a [[Limits|Limit]]. Let $U$ be an open [[Subsets|Subset]] of $\mathbb{R}^n$ and $f : U \rightarrow \mathbb{R}$ a function. The partial derivative of $f$ at the point $a = (a_1, \dots , a_n) \in U$ with respect to the $i$-th variable $x_i$ is defined as
$$\frac{ \partial }{ \partial x_i} f(a) = \lim_{h \rightarrow 0}{ \frac{f(a + he_i) - f(a)}{h} }$$