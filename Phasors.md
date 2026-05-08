---
tags:
  - EE220
---
A phasor is a [[Complex numbers|Complex number]] representing a sinusoidal function whose amplitude $A$ and initial phase $\theta$ are time-invariant and whose angular frequency $\omega$ is fixed.

A common application is in the steady-state analysis of an electrical network powered by an [[Alternating current]] where all signals are assumed to be sinusoidal with a common frequency.

Phasor notation is a mathematical notation used in electronics engineering and electrical engineering. A vector whose polar coordinates are magnitude $A$ and angle $\theta$ is written $A \angle \theta$.  $1 \angle \theta$ can represent either the vector $\langle \cos{ \theta } , \sin{ \theta } \rangle$ or the complex number $\cos{ \theta } + j \sin{ \theta } = e^{j \theta }$, according to [[Euler's formula]] with $j^2 = -1$, both of which have magnitudes of $1$.

A real-valued sinusoid with a constant amplitude, frequency, and phase has the form:
$$A \cos{ \omega t + \theta }$$

where only parameter $t$ is time-varient. The inclusion of an imaginary component:
$$j \cdot A \sin{ \omega t + \theta }$$

gives it, in accordance with Euler's formula, the factoring property:
$$A \cos{ \omega t + \theta } + j \cdot A \sin{ \omega t + \theta } = Ae^{j( \omega t + \theta )} = Ae^{j \theta } \cdot e^{j \omega t}$$

whose real part is the original sinusoid. The benefit of the complex representation is that linear operations with other complex representations produces a complex result whose real part reflects the same linear operations with the real parts of the other complex sinusoids. Furthermore, all the mathematics can be done with just the phasors $Ae^{j \theta }$. and the common factor $e^{j \omega t}$ is reinserted prior to the real part of the result.
