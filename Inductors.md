---
tags:
  - EE220
aliases:
  - Inductor
---
An inductor is a passive two-terminal electrical component that stores energy in a [[Magnetic fields|Magnetic field]] when an [[Electric current]] flows through it.

## Current Voltage Relation
Because the induced voltage is positive at the current's exit terminals as the reference point for the voltage $V(t)$ at the current's entrance terminal, the derivative form of this current-voltage relationship is then:
$$V(t) = L \frac{dI(t)}{dt}$$

The integral form of this current-voltage relationship, starting at time $t_0$ with some initial current $I(t_0),$ is then:
$$I(t) = I(t_0) + \frac{1}{L} \int_{t_0}^t{V( \tau ) \space d \tau }$$

The dual of the inductor is the [[Capacitors|Capacitor]], which stores energy in an [[Electric fields|Electric field]] rather than a magnetic field.

## Energy Stored in an Inductor
The total [[Electric energy]] $W$ stored in an inductor is equal to the total [[Work]] required to establish the current through the inductor.
$$W = \frac{1}{2}LI_0^2$$

## Parallel Combination
The equivalent inductance of inductors in parallel is
$$\frac{1}{L_{ \text{ eq } }} = \frac{1}{L_1} + \frac{1}{L_2} + \frac{1}{L_3} + \dots$$

## Series Combination
The equivalent inductance of inductors in series is
$$L_{ \text{ eq } } = L_1 + L_2 + L_3 + \dots$$