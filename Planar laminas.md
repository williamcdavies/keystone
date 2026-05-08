---
tags:
  - MATH283
---
A planar lamina is defined as a figure $D$ of a finite area in a plane, with some mass $m$.

This is useful in calculating moments of inertia or centre of mass for a constant [[Density]], because the mass of a lamina is proportional to its area. In a case of a variable density, given by some surface density function $\rho (x, y)$, the mass $m$ of the planar lamina $D$ is a planar integral of $\rho$ over the figure:
$$m = \int{ \int_D{ \rho (x, y) \space dx} \space dy}$$

The centre of mass of the lamina is at the point
$$( \frac{M_y}{m} , \frac{M_x}{m} )$$

Where $M_y$ is the moment of inertia about the $y$-axis and $M_x$ is the moment of inertia about the $x$-axis:
$$M_y = \int{ \int_D{x \rho (x, y) \space dx} \space dy}$$
$$M_x = \int{ \int_D{ y \rho (x, y) \space dx} \space dy}$$

with integration taken over a planar domain $D$.