---
tags:
  - CS365
---
Modular exponentiation is exponentiation performed over a modulus. It is written $b^n \bmod m$. When $b$, $n$, or $m$ are sufficiently large integers, the algorithm below is used:

```cpp
Algorithm:

procedure modular exponentiation(b: integer, n = (a_{k - 1}a_{k - 2} ... a_1a_0)_2, m: positive integers)

x := 1
power := b mod m
for i := 0 to k - 1
	if a_i = 1 then x:= (x * power) mod m
	power := (power * power) mod m
return x {x equals b^n mod m}
```