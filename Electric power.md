---
tags:
  - EE220
---
Electric power is the rate with respect to time at which [[Electric energy]] is supplied or absorbed:
$$\begin{align}
p \space \left[ W \right] &= \frac{dw}{dt} \space \left[ \frac{J}{s} \right] \\\\
&= \frac{dw}{dt} = \frac{dw}{dq} \cdot \frac{dq}{dt} = v \cdot i
\end{align}$$

If the reference directions of [[Electric voltage]] and [[Electric current]] adhere to the passive convention, the power $p = vi$ is the power absorbed by the circuit element.

If the reference directions of electric voltage and electric current do not adhere to the passive convention, the power $p = vi$ is the power supplied by the circuit element.

```
A voltage source v = 10cos(t) V is connected across a resistor of 10 ohms. Find the power delivered to the resistor.
```

> [!example]
Since $p = vi = Ri^2 = \frac{v^2}{R}$, the power delivered to the resistor is $\frac{(10 \cos{t} )^2}{10} = 10 \cos^2{t}$.