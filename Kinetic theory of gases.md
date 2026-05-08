---
tags:
  - PHYS181
---
The kinetic theory of gases is a simple classical model of the thermodynamic behaviour of gases. It treats a gas as composed of numerous particles of consistent random motion.

Consider a gas particle traveling at velocity $v_i$, along the $\vec{i}$ in an enclosed volume with characteristic length, $L_i$, cross-sectional area, $A_i$, and volume, $V = A_iL_i$. The gas particle encounters a boundary after characteristic time
$$t = \frac{L_i}{v_i}$$

The [[Linear momentum]] of the particle can then be described as
$$p_i = mv_i = \frac{mL_i}{t}$$

We combine the above with [[Newton's second law of motion]], which states that the force experienced by a particle is related to the time rate of its momentum such that 
$$F_i = \frac{dp_i}{dt} = \frac{mL_i}{t^2} = \frac{mv_i^2}{L_i}$$

Now consider a large number, $N$, of gas particle with random orientation in a three-dimensional volume. Because the orientation is random, the average particle speed, $v$, in every direction is identical
$$v^2 = \vec{v}_x^2 = \vec{v}_y^2 = \vec{v}_z^2$$

Further, assume that the volume is symmetrical about its three dimension, $\vec{i}$, $\vec{j}$, $\vec{k}$, such that
$$v = v_i = v_j = v_k$$
$$F = f_i = F_j = F_k$$
$$A = A_i = A_j = A_k$$

The total surface area on which the gas particles act is therefore
$$A = 3 \cdot A_i$$

The [[Pressure]] exerted by the collisions of the $N$ gas particles with the surface can then be found by adding the force contribution of every particle and dividing by the interior surface area of the volume,
$$P = \frac{N \overline{F} }{A} = \frac{NLF}{V}$$
$$\rightarrow PV = NLF = \frac{N}{3} mv^3$$

The total translational kinetic energy $K_t$ of the gas is defined as
$$K_t = \frac{N}{2} mv^2$$

providing the result
$$PV = \frac{2}{3} K_t$$

Rewriting the above result for the pressure as $PV = \frac{Nmv^2}{3}$, we may combine it with the [[Ideal gas law]] to obtain
$$k_BT = \frac{mv^2}{3}$$

which leads to a simplified expression of the average translational kinetic energy per molecule
$$\frac{1}{2} mv^2 = \frac{3}{2} k_BT$$

The translational kinetic energy of the system is $N$ times that of a molecule, namely $K_t = \frac{1}{2} Nmv^2$. The [[Temperature]], $T$ is related to the translational kinetic energy by the description above, resulting in
$$T = \frac{1}{3} \frac{mv^2}{k_B}$$

which becomes
$$T = \frac{2}{3} \frac{K_t}{Nk_B}$$

Equation $3$ is one important result of the kinetic theory: The average molecular kinetic energy is proportional to the ideal gas law's absolute temperature. From equations $1$ and $3$, we have 
$$PV = \frac{2}{3} K_t$$