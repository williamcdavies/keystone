---
tags:
  - EE220
---
The frequency-domain refers to the analysis of mathematical functions or signals with respect to frequency (and possibly phase) rather than time. A [[Time-domain]] graph shows how a single changes over time, whereas a frequency-domain graph shows how the signal is distributed within different frequency bands over a range of frequencies. A complex valued frequency-domain representation consists of both the magnitude and the phase of a set of sinusoids at the frequency components of the signal. Although it is common to refer to the magnitude portion as the frequency response of a signal, the phase portion is required to uniquely define the signal.

## Transformation from the Time-Domain to the Frequency-Domain
1. Write the function in the time domain, $y(t)$, as a cosine waveform with a phase angle $\phi$ as
$$y(t) = Y_m \cos{ \omega t + \phi }$$
2. Express the cosine waveform as the real part of a complex quantity by using [[Euler's identity]] so that
$$y(t) = \text{ Re } \{ Y_me^{j( \omega t + \phi )} \}$$
3. Drop the real part notation.
4. Suppress the $e^{j \omega t}$ while noting the value of $\omega$ for later use, obtaining the phasor
$$\vec{Y} = Y_me^{j \phi } = Y_m \angle \phi$$