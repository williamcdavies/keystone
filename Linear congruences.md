---
tags:
  - CS365
---
Linear congruences are congruences of the form $ax \equiv b \pmod{m}$ where $m$ is a positive integer, $a$ and $b$ are integers, and $x$ is a variable. Solutions of a linear congruence only exist when $\ text{ gcd } (a, m)$ divides $b$ ($b \bmod \text{ gcd } (a, m) = 0$).

The primary strategy for solving linear congruencies makes use of [[Euclid's algorithm]] and [[Bézout's identity]] to find a multiplicative inverse $a \bmod m$. A multiplicative inverse of $a \bmod m$ is the Bézout coefficient $s$ where $sa + tm = \text{ gcd } (a, m)$.

```
What are the solutions of the linear congruence 17x \equiv 3 (mod 29)?
```

> [!example]
Determine the greatest common divisor for $a$ and $m$:
> $$\begin{align}
\text{ gcd } (a, m) &= \text{ gcd } (17, 29) \\\\
\text{ gcd } (17, 29) &= \text{ gcd } (29, 17) \\\\
\text{ gcd } (29, 17) &= \text{ gcd } (17, 12) \text{ as } (29 = (17 \cdot 1) + 12) \\\\
\text{ gcd } (17, 12) &= \text{ gcd } (12, 5) \text{ as } (17 = (12 \cdot 1) + 5) \\\\
\text{ gcd } (12, 5) &= \text{ gcd } (5, 2) \text{ as } (12 = (5 \cdot 2) + 2) \\\\
\text{ gcd } (5, 2) &= 1 \text{ as } (5 = (2 \cdot 2) + 1)
\end{align}$$
>
Determine whether solutions exist for the linear congruence $17x \equiv 3 \pmod{29}$:
> $$\begin{align}
b \bmod \text{ gcd } (a, m) &= 3 \bmod \text{ gcd } (17, 29) \\\\
3 \bmod \text{ gcd } (17, 29) &= 3 \bmod 1 \\\\
3 \bmod 1 &= 0
\end{align}$$
>
Since $\text{ gcd } (17, 29) = 1$ and $3 \bmod \text{ gcd } (17,29) = 0$, one solution exists for the linear congruence $17x \equiv 3 \pmod{29}$.
>
Determine the remainder equivalences from Euclid's algorithm:
> $$\begin{align}
29 &= (17 \cdot 1) + 12 \\\\
12 &= 29 - (17 \cdot 1) \\\\
17 &= (12 \cdot 1) + 5 \\\\
5 &= 17 - (12 \cdot 1) \\\\
12 &= (5 \cdot 2) + 2 \\\\
2 &= 12 - (5 \cdot 2) \\\\
5 &= (2 \cdot 2) + 1 \\\\
1 &= 5 - (2 \cdot 2)
\end{align}$$
>
Determine the Bézout coefficients $s$ and $t$ for $1 = (s \cdot 17) + (t \cdot 29)$ through back substitution:
> $$\begin{align}
1 &= 5 - (2 \cdot 2) \\\\
1 &= 5 - (2 \cdot [12 - (5 \cdot 2)]) \\\\
1 &= 5 - (2 \cdot 12) + (2 \cdot 5 \cdot 2) \\\\
1 &= 5 - (2 \cdot 12) + (5 \cdot 4) \\\\
1 &= (5 \cdot 5) - (2 \cdot 12) \\\\
1 &= (5 \cdot [17 - (12 \cdot 1)]) - (2 \cdot 12) \\\\
1 &= (5 \cdot 17) - (5 \cdot 12 \cdot 1) - (2 \cdot 12) \\\\
1 &= (5 \cdot 17) - (5 \cdot 12) - (2 \cdot 12) \\\\
1 &= (5 \cdot 17) - (7 \cdot 12) \\\\
1 &= (5 \cdot 17) - (7 \cdot [29 - (17 \cdot 1)]) \\\\
1 &= (5 \cdot 17) - (7 \cdot 29) + (7 \cdot 17 \cdot 1) \\\\
1 &= (5 \cdot 17) - (7 \cdot 29) + (7 \cdot 17) \\\\
1 &= (12 \cdot 17) - (7 \cdot 29) \\\\
1 &= (12 \cdot 17) + (-7 \cdot 29)
\end{align}$$
> 
Since $1 = (12 \cdot 17) + (-7 \cdot 29)$, $12$ is a multiplicative inverse $s$ of $17 \bmod 29$.
>
Solve the linear congruence for $x$:
> $$\begin{align}
17x &\equiv 3 \pmod{29} \\\\
(12)(17x) &\equiv (12)(3) \pmod{29} \\\\
x &\equiv 36 \pmod{29} \\\\
x &\equiv 7 \pmod{29}
\end{align}$$

