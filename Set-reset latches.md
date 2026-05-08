---
tags:
  - CPE201
---
Set-reset latches are [[Bistable multivibrators]] designed with inputs $S$ and $R$. Input $S$  sets output $Q$ to $1$, while input $R$ resets output $Q$ to $0$. When both $S$ and $R$ are at $1$, the latch enters an undefined state. To accomplish this, set-reset latches are designed with with two cross-coupled, NOR (active high) or NAND (active low), gates that produce a regenerative feedback loop.

```
Set-reset latch truth table:

| $S'$ | $R'$ | $Q$  | $Q'$ |
|:----:|:----:|:----:|:----:|
|  1   |  1   | $NC$ | $NC$ | <--- no change
|  0   |  1   |  1   |  0   | <--- latch set
|  1   |  0   |  0   |  1   | <--- latch reset
|  0   |  0   |  1   |  1   | <--- invalid state

```

## Gated Set-Reset Latches
Unlike standard set-reset latches, gated set-reset latches are level-sensitive. As such, a third input $EN$ needs to enter an active state in order for inputs $S$ and $R$ to take effect.