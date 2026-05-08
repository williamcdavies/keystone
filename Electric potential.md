---
tags:
  - PHYS181
---
Electric potential is the amount of [[Work]] needed to move a unit charge from a reference point to a specific point against an [[Electric fields|Electric field]].

An electric potential at point $\vec{r}$ is a static electric field $\vec{E}$ is given by the line integral
$$V_E = -\int_C{ \vec{E} \cdot dl}$$

where $C$ is an arbitrary path from some fixed reference point to $\vec{r}$. The line integral above does not depend on the specific path $C$ chosen but only on its endpoints, making $V_E$ well-defined everywhere. The [[Gradient theorem]] then allows us to write:
$$\vec{E} = -\nabla V_{ \vec{E} }$$

## Electric Potential due to a Point Charge
The electric potential arising from a point charge, $Q$, at a distance, $r$, from the location of $Q$ is observed to be
$$V_{ \vec{E} } = \frac{1}{4 \pi \epsilon_0} \frac{Q}{r} = k_e \frac{Q}{r}$$

where $\epsilon_0$ is the [[Permittivity of free space]]. $V_{ \vec{E} }$ is known as the Coulomb potential.

The electric potential at any location, $\vec{r}$, in a system of point charges is equal to the sum of the individual electric potentials due to every point charge in the system. The potential of a set of discrete point charges $q_i$ at points $\vec{r}_i$ becomes
$$V_{ \vec{E} }( \vec{r} ) = \frac{1}{4 \pi \epsilon_0} \sum_{i = 1}^n{ \frac{q_i}{ \text{ | } \vec{r} - \vec{r}_i \text{ | } } }$$

and the potential of a continuous charge distribution $\rho( \vec{r} )$ becomes
$$V_{ \vec{E} }( \vec{r} ) \int_R{ \frac{ \rho( \vec{r} ') }{ \text{ | } \vec{r} - \vec{r} ' \text{ | } } \space d^3r'}$$