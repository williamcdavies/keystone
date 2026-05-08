---
tags:
  - CS365
---
The Chinese remainder theorem states that if one knows the remainders of the [[Euclidean division]] of an integer $n$ by several integers, then one can determine uniquely the remainder of the division of $n$ by the product of these integers, under the condition that the divisors are pairwise coprime.

Given pairwise coprime integers $n_1$, $n_2$, $\dots$, $n_K$ and arbitrary integers $a_1$, $a_2$, $\dots$, $a_k$, the system of simultaneous congruences 
$$\begin{align}
x &\equiv a_1 \pmod{n_1} \\\\
x &\equiv a_2 \pmod{n_2} \\\\
&\vdots \\\\
x &\equiv a_k \pmod{n_3}
\end{align}$$
has a solution, and the solution is unique modulo $N = n_1n_2 \dots n_k$.
