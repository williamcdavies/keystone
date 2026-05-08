---
tags:
  - MATH283
---
A surface integral is a generalisation of multiple integrals to integration over surfaces. It can be thought of as the double integral analogue of the line integral.

## Surface Integrals of Scalar Fields
Assume that $f$ is a scalar or vector field defined on a surface $S$. To find an explicit formula for the surface integral of $f$ over $S$, we need to parameterise $S$. Let such a parameterisation $\vec{r}(s, t)$, where $(s, t)$ varies in some region $T$ in the plane. Then, the surface integral is given by 
$$\int{ \int_S{f \space dS} } = \int{ \int_T{f( \vec{r}(s,t) ) \left| \left| \frac{ \partial \vec{r} }{ \partial s} \times \frac{ \partial \vec{r} }{ \partial t} \right| \right| \space ds} \space dt }$$

## Surface integrals of Vector Fields
Consider a vector field $\vec{v}$ on a surface $S$, that is, for each $\vec{r} = (x, y, z)$ in $S$, $\vec{v}( \vec{r} )$ is a vector.

The integral of $\vec{v}$ on $S$ was defined in the previous section. Suppose now that it is desired to integrate only the normal component of the vector field over the surface, the result being a scalar, usually called the flux passing through the surface. For example, imagine that we have a fluid flowing through $S$, such that $\vec{v}( \vec{r} )$ determines the velocity of the fluid at $\vec{r}$. The flux is defined as the quantity of fluid flowing through $S$ per unit time. 

This illustration implies that if the vector field is tangent to $S$ at each point, then the flux is zero because the fluid just flows parallel to $S$, and neither in nor out. This also implies that if $\vec{v}$ does not just flow along $S$, that is, if $\vec{v}$ has both a tangential and a normal component, then only the normal component contributes to the flux. Based on this reasoning, to find the flux, we need to take the [[Dot products|Dot product]] of $\vec{v}$ with the unit surface normal $n$ to $S$ at each point, which will give us a scalar field, and integrate the obtained field as above. In other words, we have to integrate $\vec{v}$ with respect to the surface element $ds \vec{n} \space ds$, which is the vector normal to $S$ at the given point, whose magnitude is $ds = \text{ || } d \vec{s} \text{ || }$.

We find the formula
$$\begin{align}
\int{ \int_S{ \vec{v} \cdot d \vec{s}} } &= \int{ \int_S{( \vec{v} \cdot \vec{n}) \space ds} } \\\\
&= \int{ \int_T{ \vec{v}( \vec{r}(s, t) ) \cdot \left( \frac{ \partial \vec{r} }{ \partial s} \times \frac{ \partial \vec{r} }{ \partial t} \right) \space ds} \space dt}
\end{align}$$