---
tags:
  - PHYS181
---
The Hall effect is the production of a potential difference across an electrical conductor that is transverse to an [[Electric current]] in the conductor and to an applied [[Magnetic fields|Magnetic field]] perpendicular to the electric current.

In deriving an expression for the Hall voltage, first note that the magnetic force exerted on the carriers has magnitude $qv_dB$. In equilibrium this force is balanced by the electric force $qE_H$, where $E_H$ is the magnitude of the electric field due to the charge separation. Therefore,
$$\begin{align}
qv_dB &= qE_H \\\\
E_H &= v_dB
\end{align}$$

If $d$ is the width of the conductor, the Hall voltage is
$$\Delta V_H = E_Hd = v_dBd$$

Therefore, the measured Hall voltage gives a value for the [[Drift velocity]] of the charge carriers if $d$ and $B$ are known.

We can obtain the charge-carrier density $n$ by measuring the electric current in the sample. From $I = nqv_dA$, we can express the drift velocity as
$$v_d = \frac{I}{nqA}$$

where $A$ is the cross-sectional area of the conductor. Substituting $\frac{1}{nqA}$ into $\Delta V_H = v_dBd$ and solving for $B$ gives
$$B = \frac{nqA}{Id} \Delta V_H$$

Because $A = td$, where $t$ is the thickness of the conductor, we can also express $B = \frac{nqA}{Id} \Delta V_H$ as
$$B = \frac{nqt}{I} \Delta V_H$$

This relationship shows that a properly calibrated conductor can be used to measure the magnitude of any unknown magnetic field.