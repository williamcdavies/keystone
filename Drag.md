---
tags:
  - PHYS180
---
In [[Fluid dynamics]], drag or fluid resistance is a force acting opposite to the relative motion of any object moving with respect to a surrounding fluid.

Unlike other resistive forces, such as [[Friction]], the drag force depends on velocity. Drag force is proportional to the velocity for low-speed flow and the squared velocity for high speed flow, where the distinction between low and high speed is measured by the [[Reynolds number]] ($\text{ R } e$).

Drag forces always tend to decrease fluid velocity relative to the solid object in the fluid's path.

## The Drag Equation
Drag depends on the properties of the fluid and on the size, shape, and speed of the object. One way to express this is by means of the drag equation: 
$$F_D = \frac{ \rho v^2 C_D A}{2}$$

where:
- $F_D$ is the quadratic drag force,
- $\rho$ is the [[Density]] of the fluid,
- $v$ is the speed of the object relative to the fluid
- $A$ is the cross sectional area, and
- $C_D$ is the drag coefficient - a dimensionless number.

### With Relatively High Reynolds Numbers ($\text{ R } e > \space \sim 1000$)
As described above, the drag equation with a constant drag coefficient gives the force experienced by an object moving through a fluid with a relatively high Reynolds number. This is called quadratic drag.

#### Power
Under the assumption that the fluid is not moving relative to the currently used reference system, the power required to overcome the aerodynamic drag is given by: 
$$P_d = F_D \cdot v = \frac{ \rho v^3 C_D A}{2}$$

The power needed to push an object through a fluid increases as the cube of the velocity. A motor-vehicle may require only 10 horsepower to overcome aerodynamic drag at $80$ $\frac{ \text{ km } }{ \text{ h } }$ but requires $80$ horsepower to overcome aerodynamic drag at $160$ $\frac{ \text{ km } }{ \text{ h } }$. When the speed of an object doubles, the drag force acting on that object quadruples.

### With Relatively Low Reynolds Numbers ($\text{ R } e < \space \sim 1$)
The equation for viscous resistance or linear drag is appropriate for objects or particles moving through a fluid with a relatively low Reynolds number and is modelled by: 
$$F_D = -bv$$

where:
- $F_D$ is the linear drag force,
- $b$ is a constant that depends on the material properties of the object and fluid, as well as the geometry of the object, and
- $v$ is the velocity of the object.

When an object falls from rest, its velocity as a function of time will be 
$$v(t) = \frac{( \rho - \rho_o )Vg}{b} \left(1 - e^{ \frac{-bt}{m} } \right)$$ 

where:
- $\rho$ is the density of the object,
- $\rho_o$ is the density of the fluid,
- $V$ is the volume of the object,
- $g$ is the acceleration due to gravity, and
- $m$ is the mass of the object.

The velocity asymptotically approaches the terminal velocity 
$$v_t = \frac{( \rho - \rho_o )Vg}{b}$$

For a given $b$, denser objects fall more quickly.