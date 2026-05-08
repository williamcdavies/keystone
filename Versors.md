---
tags:
  - CS381
---
A versor is a [[Quaternions|Quaternion]] whose norm is one, also known as a unit quaternion. Each versor has the form
$$u = \text{exp}(a \mathbf{r} ) = \cos{a} + \mathbf{r} \sin{a}, \quad \mathbf{r}^2 = -1, \quad a \in [0, \pi ]$$

The mapping $q \rightarrow u^{-1}qu$ corresponds to 3-dimensional rotation, and has the angle $2a$ about the axis $\mathbf{r}$ in axis-angle representation.