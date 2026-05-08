---
tags:
  - PHYS181
---
## Self Capacitance
Every isolated conductor exhibits capacitance, called self capacitance. It is measured by the amount of electric charge that must be added to an isolated conductor to raise its [[Electric potential]] by one unit of measurement, e.g., one volt. The reference point for this potential is a theoretical hollow conducting sphere, of infinite radius, wit the conductor centred inside this sphere.

Self capacitance of a conductor is defined by the ratio of charge and electric potential:
$$C = \frac{q}{V}$$

where $q$ is the charge held, $V = k_e \int{ \frac{ \sigma }{r} \space dS}$ is the electric potential, $\sigma$ is the surface charge density, $dS$ is the infinitesimal element of area on the surface of the conductor, over which the surface charge density is integrated, $r$ is the length from $dS$ to a fixed point $M$ on the conductor, $k_e$ is the [[Coulomb constant]].

Using this method, the self capacitance of a conducting sphere of radius $R$ in free space is:
$$C = 4 \pi \epsilon_0 R$$

## Mutual Capacitance
A common form is a parallel-plate capacitor, which consists of two conductive plates insulated from each other. In a parallel plate capacitor, capacitance is very nearly proportional to the surface area of the conductor plates and inversely proportional to the separation distance between the plates.

If the charges on the plates are $+q$ and $-q$, and $V$ gives the [[Electric voltage]] between the plates, then the capacitance $C$ is given by
$$C = \frac{q}{V}$$

which gives the electric voltage/current relationship
$$i(t) = C \frac{dv(t)}{dt} + V \frac{dC}{dt}$$

where $\frac{dv(t)}{dt}$ is the instantaneous rate of change of voltage, and $\frac{dC}{dt}$ is the instantaneous rate of change of the capacitance. For most applications, the change in capacitance over time is negligible, so the formula reduces to:
$$i(t) = C \frac{dv(t)}{dt}$$

The energy stored in a capacitor is found be integrating the [[Work]] $W$:
$$W_c = \frac{1}{2} CV^2$$

## Capacitors
The capacitance can be calculated if the geometry of the conductors and the dielectric properties of the insulator between the conductors are know. Capacitance is proportional to the area of overlap and inversely proportional to the separation between conducting sheets. The close the sheets are to each other, the greater the capacitance.

An example is the capacitance of a capacitor constructed of two parallel plates both of area $A$ separated by a distance $d$. If $d$ is sufficiently small with respect to the smallest chord of $A$, there holds, to a high level of accuracy:
$$C = \epsilon_0 \epsilon_r \frac{A}{d}$$

where $C$ is the capacitance, in farads, $A$ is the area of overlap of the two plates, $\epsilon_0$ is the [[Permittivity of free space]], $\epsilon_r$ is the [[Relative permittivity]], and $d$ is the separation between the plates.

## Parallel Combination
The equivalent capacitance of capacitors in parallel is
$$C_{ \text{ eq } } = C_1 + C_2 + C_3 + \dots$$

## Series Combination
The equivalent capacitance of capacitors in series is
$$\frac{1}{C_{ \text{ eq } }} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3} + \dots$$

## Charging a Capacitor
If a capacitor is charged with a battery through a resistor of resistance $R$, the charge on the capacitor and the [[Electric current]] in the circuit vary in time according to the expressions
$$q(t) = Q_{ \text{ max } }(1 - e^{ \frac{-t}{RC} })$$
$$i(t) = \frac{ \epsilon }{R} e^{ \frac{-t}{RC} }$$

where $Q_m = C \epsilon$ is the maximum charge on the capacitor. The product $RC$ is called the time constant $\tau$ of the circuit

## Discharging a Capacitor
If a charged capacitor of capacitance $C$ is discharged through a resistor of resistance $R$, the charge and electric current decrease exponentially in time according to the expressions
$$q(t) = Q_i e^{ \frac{-t}{RC} }$$
$$i(t) = -\frac{ Q_i }{RC} e^{ \frac{-t}{RC} }$$

where $Q_i$ is the initial charge on the capacitor and $\frac{Q_i}{RC}$ is the initial electric current in the circuit.
