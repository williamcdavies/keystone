---
tags:
  - MATH181
---
If a real-valued function $f$ is continuous on the closed interval $[a,b]$, then $f$ must attain at least one maximum and at least one minimum in $[a,b]$. That is, there exist numbers $c$ and $d$ in $[a,b]$ such that: $f(c) \geq f(x) \geq f(d) \forall x \in [a,b]$.

## Proof

### Proof of the Boundedness Theorem
If it is assumed that $f(x)$ is continuous on $[a,b]$ then it is bounded on $[a,b]$.

Suppose the function $f$ is not bounded above on the interval $[a,b]$. Then, for every natural number $n$, there exists $x_n \in [a,b]$ such that $f(x_n) > n$. This defines a sequence $(x_n)_{n \in \mathbb{N} }$. Since $[a,b]$ is bounded, the [[Bolzano-weierstrass theorem]] implies that there exists a convergent subsequence $(x_{n_k})_{k \in \mathbb{N} }$ of $(x_n)$. Denote its limit by $x$. As $[a,b]$ is closed, it contains $x$. Since $f$ is continuous at $x$, it is known that $f(x_{n_k})$ converges to the real number $f(x)$. However, $f(x_{n_k}) > n_k \geq k$ for every $k$, which implies that $f(x_{n_k})$ diverges to $+\infty$, a contradiction. Therefore, $f$ is bounded above on $[a,b]$. 

### Proof of the Extreme Value Theorem
By the [[Boundedness theorem]], $f$ is bounded from above, hence by the [[Dedekind-completeness]] of the real numbers, the supremum $M$ of $f$ exists. It is necessary to find a point $d$ in $[a,b]$ such that $M = f(d)$. Let $n$ be a natural number. As $M$ is the least upper bound, $M - \frac{1}{n}$ is not an upper bound for $f$. Therefore, there exists $d_n$ in $[a,b]$ so that $M - \frac{1}{n} < f(d_n)$. This defines a sequence {$d_n$}. Since $M$ is an upper bound for $f$, we have $M - \frac{1}{n} < f(d_n) \leq M$ for all $n$. Therefore, the sequence {$f(d_n)$} converges to $M$.

The Bolzano-Weierstrass theorem tells that there exists a subsequence {$d_{n_k}$}, which converges to some $d$ and, as $[a,b]$ is closed, $d$ is in $[a,b]$. Since $f$ is continuous at $d$, the sequence {$f(d_{ n_k })$} converges to $f(d)$. But {$f(d_{n_k})$} is a subsequence of {$f(d_n)$} that converges to $M$, so $M = f(d)$. Therefore, $f$ attains its supremum $M$ at $d$.