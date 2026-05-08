---
tags:
  - CPE201
---
Jack-Kilby flip-flops, or J-K flip-flops, are [[Bistable multivibrators]] similar to [[Set-reset flip-flops]]. However, Jack-Kilby flip-flops were designed to solve the two primary problems that set-reset flip-flops and [[Set-reset latches]] run into:
- The $S = 0$ and $R = 0$ condition results in an invalid state
- If $S$ or $R$ change when the enable bit $EN$ is active, the correct latching action may not occur

As such, Jack-Kilby flip-flops are constructed with an additional clock input circuit that prevents the invalid output condition $S = R = 0$. Now, when inputs $S$ and $R$ are $1$, a toggle action is completed, toggling the latch state of the circuit.

```
Jack-Kilby flip-flop truth table

| $CLK$  | $J$ | $K$ | $Q$ | $Q'$ |
|:------:|:---:| --- |:---:|:----:|
|  $X$   |  0  | 0   |  1  |  0   | <--- memory no change
|  $X$   |  0  | 0   |  0  |  1   | <--- memory no change
| $->\_$ |  0  | 1   |  1  |  0   | <--- reset $Q$ >> $0$
|  $X$   |  0  | 1   |  0  |  1   | <--- reset $Q$ >> $0$
| $->\_$ |  1  | 0   |  0  |  1   | <--- set $Q$ >> $1$
|  $X$   |  1  | 0   |  1  |  0   | <--- set $Q$ >> $1$
| $->\_$ |  1  | 1   |  0  |  1   | <--- latch toggle
| $->\_$ |  1  | 1   |  1  |  0   | <--- latch toggle

```


