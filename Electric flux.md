---
tags:
  - PHYS181
---
Electric flux is the quantification of electric field lines passing through a given surface. Since the total number of electric field lines produced by an [[Electric fields|Electric field]] is proportional to the magnitude of the electric field, electric flux can modelled by 
$$\Phi_E = EA_{ \perp } = EA \cos{ \theta }$$

where $E$ is the magnitude of the electrical field, $A$ is the surface area, and $\theta$ is the angle between $A$ and $A_{ \perp }$.

Consider a general surface divided into a large number of small elements, each of area $\Delta A_i$. It is convenient to define a vector $\Delta \vec{A}_i$ whose magnitude represents the area of the $i$th element of the large surface and whose direction is defined to be perpendicular to the surface. The electric field $\vec{E}_i$ at the location of this element makes an angle $\theta_i$ with the vector  $\Delta \vec{A}_i$. The electric flux $\Phi_{E,i}$ through this element is
$$\Phi_{E,i} = E_i \Delta A_i \cos{ \theta_i } = \vec{E}_i \cdot \Delta \vec{A}_i$$

Summing the contributions of all elements gives an approximation to the total flux through the surface:
$$\Phi_E \approx \sum{ \vec{E}_i \cdot \Delta \vec{A}_i }$$

As the area of each element approaches zero and the total number of elements approaches infinity, the sum can be replaced by an integral which provides the general definition of electric flux:
$$\Phi_E \equiv \int_S{ \vec{E} \cdot d \vec{A} }$$
