---
tags:
  - CS658
---
The Minkowski distance of order $p$ (where $p$ is an integer) between two points
$$X = (x1, x2, \dots, x_n) \text{ and } Y = (y_1, y_2, \dots, y_n) \in \mathbb{R}^n$$

is defined as:
$$D(X, Y) = ( \sum_{i = 1}^n{ \text{ | } x_i - y_i \text{ | }^p } )^{ \frac{1}{p} }$$

For $p \geq 1$, the Minkowski distance is a metric as a result of the Minkowski inequality. When $p < 1$, the distance between $(0, 0)$ and $(1, 1)$ is $2^{ \frac{1}{p} } > 2$, but the point $(0, 1)$ is at a distance $1$ from both these points. Since this violates the triangle inequality, for $p < 1$ it is note a metric. However, a metric can be obtained from these values by simply removing the exponent of $\frac{1}{p}$. The resulting metric is also an F-norm.

Minkowski distance is typically used with $p$ being $1$ or $2$, which correspond to the [[Manhattan distances|Manhatten distance]] and the [[Euclidean distances|Euclidean distance]], respectively. In the limiting case of $p$ reaching infinity, we obtain the [[Chebyshev distances]]:
$$\lim_{p \rightarrow \infty }{( \sum_{i = 1}^n{ \text{ | } x_i - y_i \text{ | }^p } )^{ \frac{1}{p} }} = \max_{i = 1}^n{ \text{ | } x_i - y_i \text{ | } }$$

Similarly, for $p$ reaching negative infinity, we have:
$$\lim_{p \rightarrow -\infty }{( \sum_{i = 1}^n{ \text{ | } x_i - y_i \text{ | }^p } )^{ \frac{1}{p} }} = \min_{i = 1}^n{ \text{ | } x_i - y_i \text{ | } }$$

The Minkowski distance can also be viewed as a multiple of the power mean of the component-wise difference between $P$ and $Q$.