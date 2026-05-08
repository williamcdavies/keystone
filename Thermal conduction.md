---
tags:
  - PHYS181
---
Thermal conduction is the diffusion of thermal energy within one material or between materials in contact. 

## Integral form
By integrating the differential form over the material's total surface $S$, we arrive at the integral form of Fourier's law: 
$$\oint{ \oint{q \cdot dS} } = -k \oint{ \oint{ \nabla T \cdot dS} }$$

where
- $Q = \oint{ \oint{q \cdot dS} }$ is the thermal power transferred by thermal conduction, time derivative of the transferred [[Heat]] $Q$
- $dS$ is an oriented surface area element 

The above differential equation, when integrated for a homogenous material of $1$-D geometry between two endpoints at constant [[Temperature]], gives the heat flow rate as
$$Q = -k \frac{ A \Delta t}{L} \Delta T$$

where
- $\Delta t$ is the time interval during which the amount of heat $Q$ flows through a cross-section of the material
- $A$ is the cross-sectional surface area
- $\Delta T$ is the temperature difference between the ends
- $L$ is the distance between the ends.