---
tags:
  - MATH181
---
If $f$ is a continuous function on the closed interval $[a,b]$, and differentiable on the open interval $(a,b)$, then there exists a point $c$ in $(a,b)$ such the tangent at $c$ is parallel to the secant line through the endpoints $(a,f(a)$ and $(b,f(b))$, that is, 
$$f'(c) = \frac{f(b) - f(a)}{b - a}$$

### Formal Statement
Let $f:[a,b] \rightarrow \mathbb{R}$ be a continuous function on the closed interval $[a,b]$ and differentiable on the open interval $(a,b)$, where $a < b$. Then there exists some $c$ in $(a,b)$ such that 
$$f'(c) = \frac{f(b) - f(a)}{b - a}$$

## Proof
The expression $\frac{f(b) - f(a)}{b - a}$ gives the slope of the line joining the points $(a,f(a))$ and $(b,f(b))$, which is a cord of the graph $f$, while $f'(x)$ gives the slope of the tangent to the curve at the point $(x,f(x))$. Thus, the mean value theorem says that given any chord of a smooth curve, we can find a point on the curve lying between the end-points of the chord such that the tangent of the curve at that point is parallel to the chord. The following proof illustrates this idea.

Define $g(x) = f(x) - rx$ where $r$ is a constant. Since $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$, the same is true for $g$. We now want to choose $r$ so that $g$ satisfies the conditions of [[Rolle's theorem]]. Namely 
$$g(a) = g(b) \longleftrightarrow r = \frac{f(b) - f(a)}{b - a}$$

By Rolle's theorem, since $g$ is differentiable and $g(a) = g(b)$, there is some $c$ in $(a,b)$ for which $g'(c) = 0$, and it follows from the equality $g(x) = f(x) - rx$ that, 
$$f'(c) = r = \frac{f(b) - f(a)}{b - a}$$