---
tags:
  - EE220
aliases:
  - Capacitor
---
A capacitor is a passive two-terminal electrical component that stores energy in an [[Electric fields|Electric field]] when an [[Electric current]] flows through it.

Capacitors are represented by a parameter called [[Capacitance]]. Capacitance occurs when two conductors are separated by a [[Dielectrics|Dielectric]]. Capacitance is a measure of the ability of a device to store energy in the form of a separated charge or electric field.

## Current-Voltage Relation
The charge on the electrodes is equal to the integral of the currents as well as proportional to the voltage. As with any antiderivative, a constant of integration is added to represent the initial voltage $V(t_0)$. This is the integral form of the capacitor equation:
$$V(t) = \frac{Q(t)}{C} = V(t_0) + \frac{1}{C} \int_{t_0}^t{I( \tau) \space d \tau }$$

Taking the derivative of this and multiplying by $C$ yields the derivative form:
$$I(t) = \frac{dQ(t)}{dt} = C \frac{dV(t)}{dt}$$

for $C$ of independent of time, [[Electric voltage]], and electric charge.

The dual of the capacitor is the [[Inductors|Inductor]], which stores energy in a [[Magnetic fields|Magnetic field]] rather than an electric field.

## Energy Stored in a Capacitor
The total [[Electric energy]] $W$ stored in a capacitor is equal to the total [[Work]] done in establishing the electric field from an uncharged state.
$$W = \int_0^Q{v(q) \space dq} = \int_0^Q{ \frac{q}{C} \space dq} = \frac{1}{2} \frac{Q^2}{C} = \frac{1}{2} VQ = \frac{1}{2} CV^2$$

## Parallel Combination
The equivalent capacitance of capacitors in parallel is
$$C_{ \text{ eq } } = C_1 + C_2 + C_3 + \dots$$

## Series Combination
The equivalent capacitance of capacitors in series is
$$\frac{1}{C_{ \text{ eq } }} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3} + \dots$$