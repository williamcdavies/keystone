---
tags:
  - CS365
---
Euclid's algorithm algorithm, also called the Euclidian algorithm, is an algorithm for finding the greatest common divisor of two numbers $a$ and $b$. 

Let $a = bq + r$, then find a number $u$ which divides both $a$ and $b$ so that $a = su$ and $b = tu$. Then $u$ also divides $r$ since $r = a - bq = su - qtu = (s - qt)u$. Similarly, find a number $v$ which divides $b$ and $r$ so that $b = s'v$ and $r = t'v$. Then $v$ divides $a$ since $a = bq + r = s'vq + t'v = (s'q + t')v$. Therefore, every common divisor of $a$ and $b$ is a common divisor of $b$ and $r$, so the procedure can be iterated.

```cpp
Algorithm:

procedure gcd(a, b : positive integers)
x := a
y := b
while y != 0
	r := x mod y
	x := y 
	y :=r
return x {gcd(a, b) is x}
```

