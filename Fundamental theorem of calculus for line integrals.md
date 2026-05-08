---
tags:
  - MATH283
---
If $\vec{F}$ is a vector field in the plane or in space and $C : t \rightarrow \vec{r}(t)$ is a curve defined on the interval $[a, b]$ then
$$\int_a^b{ \vec{F}( \vec{r}(t) ) \cdot \vec{r}'(t) \space dt}$$

is called the line integral of $\vec{F}$ along the curve $C$. The Fundamental theorem of line integrals states that if $\vec{F} = \nabla f$, then
$$\int_a^b{ \vec{F}( \vec{r}(t) ) \cdot \vec{r}'(t) \space dt} = f( \vec{r}(b) ) - f( \vec{r}(a) )$$

Let $\vec{F}(x, y) = \langle P(x, y), Q(x, y) \rangle$, where $P$ and $Q$ are continuous across the interval $[a, b]$. If $P_y = Q_x$, then there is some potential function $f(x, y)$ where $\nabla f(x, y) = \vec{F}(x, y)$.

