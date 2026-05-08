---
tags:
  - EE220
---
The time-domain is a representation of how a signal, function, or data set varies with time.

In the time-domain, the independent variable is time and the dependent variable is the value of the signal. This contrasts with the [[Frequency-domain]], where the signal is represented by its constant frequencies. For continuous-time signals, the value of the signal is defined for all real numbers representing time. For discrete-time signals, the value is known at discrete often equally-spaced, time intervals. It is commonly visualised using a graph where the $x$-axis represents time and the $y$-axis represents the signal's value.

## Transformation from the Frequency-Domain to the Time-Domain
1. Write the phasor in exponential form as
$$\vec{Y} = Y_me^{j \beta }$$
2. Reinsert the factor $e^{j \omega t}$  so that you have
$$Y_me^{j \beta }e^{j \omega t}$$
3. Reinsert the real part operator $\text{ Re }$ as
$$\text{ Re } \{ Y_me^{j \beta }e^{j \omega t} \}$$
4. Use [[Euler's identity]] to obtain the time function
$$y(t) = \text{ Re } \{ Y_me^{j( \omega t + \beta )} \} = Y_m \cos{ \omega t + \beta }$$