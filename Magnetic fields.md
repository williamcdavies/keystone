---
tags:
  - PHYS181
aliases:
  - Magnetic field
---
Magnetic fields are produced by moving electric charges and the intrinsic magnetic moments of elementary particles associated with a fundamental quantum property, their spin. Magnetic fields and [[Electric fields]] are interrelated and are both components of the electromagnetic force, one of the four fundamental forces of nature.

The strength of the magnetic force on a charge is proportional to the magnetic field through which the charge is moving:
$$\text{ | } \vec{F}_B \text{ | } \propto \text{ | } \vec{B} \text{ | }$$

The strength of the magnetic force is proportional to the magnitude of the charge:
$$\text{ | } \vec{F}_B \text{ | } \propto q \text{ | } \vec{B} \text{ | }$$

The strength of the magnetic force on a charge is proportional to the speed at which the charge is moving through the field:
$$\text{ | } \vec{F}_B \text{ | } \propto q \text{ | } \vec{v} \text{ || } \vec{B} \text{ | }$$

The strength of the magnetic force on a charge varies depending upon the relative directions of the magnetic field and the charge's velocity vector:
$$\text{ | } \vec{F}_B \text{ | } = \text{ | } q \text{ || } \vec{v} \text{ || } \vec{B} \text{ | } \sin{ \theta }$$

The direction of the magnetic force is perpendicular to both the direction of the velocity and the direction of the magnetic field:

When combining the magnitude and the direction of the magnetic force, mathematically it is written using the [[Cross products|Cross product]]:
$$\vec{F}_B = q \vec{v} \times \vec{B}$$

## Motion of a Charged Particle in a Uniform Magnetic Field
When the velocity of a charged particle is perpendicular to a uniform magnetic field, the particle moves in a circular path in a plane perpendicular to $\vec{B}$.

We use the particle under a net force model to write [[Newton's second law of motion]] for the particle:
$$\sum{F} = F_B = ma$$

Because the particle moves in a circle, we also model it as a particle in uniform circular motion and we replace the acceleration with centripetal acceleration:
$$F_B = qvB = \frac{mv^2}{r}$$

This expression leads to the following equation for the radius of the circular path:
$$r = \frac{mv}{qB}$$

That is, the radius of the path is proportional to the linear momentum $mv$ of the particle and inversely proportional to the magnitude of the charge on the particle and to the magnitude of the magnetic field. The angular speed of the particle is
$$\omega = \frac{v}{r} = \frac{qB}{m}$$

The period of the motion is equal to the circumference of the circle divided by the speed of the particle:
$$T = \frac{2 \pi r}{v} = \frac{2 \pi }{ \omega } = \frac{2 \pi m}{qB}$$

These results show that the angular speed of the particle and the period of the circular motion do not depend on the speed of the particle or on the radius of the orbit. The angular speed $\omega$ is often referred to as the cyclotron frequency because charged particles circulate at this angular frequency in the type of accelerator called a [[Cyclotrons|Cyclotron]].

## Magnetic Force Acting on a Electric Current-Carrying Conductor
For a segment of a electric current-carrying wire in a magnetic field $\vec{B}$, the average magnetic force exerted on a charge moving in the wire is $$q \vec{v}_d \times \vec{B}$$ 

The magnetic force on the wire segment of length $L$ is 
$$I \vec{L} \times \vec{B}$$

For a segment of an arbitrary electric current-carrying wire in a magnetic field $\vec{B}$, the magnetic force on any segment $d \vec{s}$ is $I \space d \vec{s} \times \vec{B}$ and is directed outward.

To calculate the total force $\vec{F}_B$ acting on an arbitrary electric current-carrying wire, we integrate over the length of the wire:
$$\vec{F}_B = I \int_a^b{d \space \vec{s} \times \vec{B} }$$

where $a$ and $b$ represent the endpoints of the wire.