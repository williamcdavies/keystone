---
tags:
  - PHYS181
aliases:
  - Electric field
---
An electric field is the electric property associated with each point in space when charge is present in any form.

The magnitude and direction of an electric field as some point $P$ is given by:
$$\vec{E} = \frac{ \vec{F}_e }{q_0}$$

where $\vec{E}$ is the component of the electric field at $q_0$ due to $q_1$, $\vec{F}_e$ is the force on the charge particle $q_0$ caused by charged particle $q_1$, and $q_0$ is the charge of some test particle.

The electrostatic force experienced by an arbitrary charge $q$ along the electric field vector $\vec{E}$ is given by:
$$\vec{F}_e = q \vec{E}$$

Therefore, the electric field vector $\vec{E}$ can be given by:
$$\vec{E} = \frac{ \vec{F}_e }{q} = k_e \frac{q}{r^2} \widehat{r}$$

where $k_e$ is the [[Coulomb constant]], $q$ is the source charge, $r$ is the distance between $q$ and some point $P$, and $\widehat{r}$ is a unit vector directed from $q$ toward $P$.

The electric field vector at some point $P$ due to a number of point charges is given by:
$$\vec{E} = k_e \sum_i{ \frac{q_i}{r_i^2} \widehat{r}_i }$$

## Electric Field Lines
The electric field vector $\vec{E}$ is tangent to the electric field line at each point. The line has direction, indicated by an arrowhead, that is the same as that of the electric field vector. The direction of the line is that of the force on a positive charge placed in the field according of the particle in a field model.

The number of lines per unit area through a surface perpendicular to the lines is proportional to the magnitude of the electric field in that region. Therefore, the field lines are close together where the electric field is strong and far apart where the field is weak.

## Motion of a Charged Particle in a Uniform Electric Field
The acceleration of a particle in a uniform electric field under a net force model is given by:
$$\vec{a} = \frac{ \vec{F} }{m} = \frac{q \vec{E} }{m}$$

where $q$ is the charge of the particle, $\vec{E}$ is the electric field vector, and $m$ is the mass of the particle.

## Continuous Charge Distribution
The electric field at some point $P$ due to a continuous charge distribution is the vector sum of the fields $\Delta \vec{E}_i$, due to all the elements $\Delta q_i$ of the charge distribution. The electric field at $P$ due to one charge element carrying charge $\Delta q$ is
$$\Delta \vec{E} = k_e \frac{ \Delta q}{r^2} \widehat{r}$$

where $r$ is the distance from the charge element to point $P$ and $\widehat{r}$ is a unit vector directed from the element toward $P$. The total electric field at $P$ due to all elements in the charge distribution is approximately
$$\vec{E} \approx k_e \sum_i{ \frac{ \Delta q_i}{r_i^2} \widehat{r}_i }$$

where the index $i$ refers to the $i$th element in the distribution. Because the number of elements is very large and the charge distribution is modelled as continuous, the total field at $P$ is
$$\vec{E} = k_e \lim_{ \Delta q \rightarrow 0}{ \sum_i{ \frac{ \Delta q_i}{r_i^2} } \widehat{r}_i } = k_e \int{ \frac{dq}{r^2} \widehat{r}}$$

The integration above is a vector operation and must be treated appropriately.

It is convenient to consider the [[Charge density]] of an object when performing such calculations.