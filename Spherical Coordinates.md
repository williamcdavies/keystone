---
tags:
  - MATH283
---
In the spherical coordinate system, a point $P$ in space is represented by the ordered triple $( \rho, \theta, \phi )$  where $\rho$ is the distance between $P$ and the origin $( \rho \neq 0)$, $\theta$ is the same angle used to describe the location in [[Cylindrical coordinates]], and $\phi$ is the angle formed by the positive $z$-axis and the line segment $\overline{OP}$ where $O$ is the origin and $0 \leq \phi \leq \pi$.

## Converting among Spherical, Cylindrical, & Rectangular Coordinates
Rectangular coordinates $(x, y, z)$, cylindrical coordinates $(r, \theta, z)$, and spherical coordinates $\rho, \theta, \phi$ of a point are related as follows:

### Convert from Spherical Coordinates to Rectangular Coordinates
These equations are used to convert from spherical coordinates to rectangular coordinates
- $x = \rho \sin{ \phi } \cos{ \theta }$
- $y = \rho \sin{ \phi } \sin{ \theta }$
- $z = \rho \cos{ \phi }$

### Convert from Rectangular Coordinates to Spherical Coordinates
These equations are used to convert from rectangular coordinates to spherical coordinates
- $\rho = \sqrt{x^2 + y^2 + z^2}$
- $\theta = \arctan{ \frac{y}{x} }$
- $\phi = \arccos{ \frac{z}{ \sqrt{x^2 + y^2 + z^2} } }$

### Convert from Spherical Coordinates to Cylindrical Coordinates
These equations are used to convert from spherical coordinates to cylindrical coordinates
- $r = \rho \sin{ \phi }$
- $\theta = \theta$
- $z = \rho \cos{ \phi }$

### Convert from Cylindrical Coordinates to Spherical Coordinates
These equations are used to convert from cylindrical coordinates to spherical coordinates
- $\rho = \sqrt{r^2 + z^2}$
- $\theta = \theta$
- $\phi = \arccos{ \frac{z}{ \sqrt{r^2 + z^2} } }$