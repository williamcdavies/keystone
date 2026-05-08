---
tags:
  - EE220
---
An operational amplifier is a DC-coupled electronic voltage amplifier with a differential input and a single-ended output.

The amplifier's differential inputs consists of a non-inverting input $v_+$ and an inverting input $v_-$. Ideally, the operational amplifier amplifies only the difference in voltage between $v_+$ and $v_-$, which is called the differential input voltage. The output voltage of the op amp $v_{ \text{ out } }$ is given by the equation
$v_{ \text{ out } } = A_{ \text{ OL } }(v_+ - v_-)$

where $A_{ \text{ OL } }$ is the open-loop gain of the amplifier. 

Since the open-loop gain $A_{ \text{ OL } }$ and input impedance $R_{ \text{ in } }$ of an ideal op-amp are infinite, the difference between $v_+$ and $v_-$ must approach $0$ to avoid voltage saturation. Similarly, the input currents $i_+$ and $i_-$ approach $0$ as $R_{ \text{ in } }$ approaches $\infty$.