---
tags:
  - EE220
---
A linear system is a system which obeys the [[Superposition principle]].

```
Consider the element represented by: v = Ri. Determine whether this element is linear.
```

> [!example]
For the element represented by $v(i) = Ri$ to be linear, the statements $v(i_1 + i_2) = v(i_1) + v(i_2) = Ri_1 + Ri_2$ and $v( \alpha i) = \alpha v(i) = \alpha Ri$ must be true. Since $v(i_1 + i_2) = R(i_1 + i_2) = Ri_1 + Ri_2$ and $v( \alpha i) = R( \alpha i) = \alpha Ri$, the element must be linear.

```
Consider the element represented by: v = i^2. Determine whether this element is linear.
```

> [!example]
For the element represented by $v(i) = i^2$ to be linear, the statements $v(i_1 + i_2) = v(i_1) + v(i_2) = i_1^2 + i_2^2$ and $v( \alpha i) = \alpha v(i) = \alpha i^2$ must be true.  Since $v(i_1 + i_2) = (i_1 + i_2)^2 = i_1^2 + 2i_1i_2 + i_2^2 \neq i_1^2 + i_2^2$ and $v( \alpha i) = ( \alpha i)^2 = \alpha^2 i^2 \neq \alpha i^2$, the element cannot be linear.