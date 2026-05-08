---
tags:
  - CS477
---
The master theorem always yields asymptotically tight bounds to recurrences of the form $T(n) = aT( \frac{n}{b} ) + f(n)$, where $n$ is the size of an input problem, $a$ is the number of subproblems in the recursion, and $b$ is the factor by which the subproblem size is reduced in each recursive call ($b > 1$). Crucially, $a$ and $b$ cannot depend on $n$. The theorem below also assumes that, as a base case for the recurrence, $T(n) = \Theta (1)$ when $n$ is less than some bound $\kappa > 0$, the smallest input size that will lead to a recursive call.

Recurrences of this form often satisfy one of the three following regimes, based on how $f(n)$ relates to $c = n^{ \log_b{a} }$

## Case $1$: $f(n) = O(n^{ \log_b{a - \epsilon } }) \mid \epsilon > 0$
If $f(n) = O(n^{ \log_b{a - \epsilon } })$ for some $\epsilon > 0$, then: $$T(n) = \Theta (n^{ \log_b{a} })$$

## Case $2$: $f(n) = \Theta (n^{ \log_b{a} } \cdot \log^{k + 1}{n} ) \mid k \geq 0$
If $f(n) = \Theta (n^{ \log_b{a} } \cdot \log^{k + 1}{n} )$ for some $k \geq 0$, then: $$T(n) = \Theta (n^{ \log_b{a} } \cdot \log^{k + 1}{n} )$$

## Case $3$: $f(n) = \Omega (n^{ \log_b{a + \epsilon } }) \mid \epsilon > 0$
If $f(n) = \Omega (n^{ \log_b{a + \epsilon } })$ for some $\epsilon > 0$, and if $a \cdot f( \frac{n}{b} ) \leq c \cdot f(n)$ for some $c < 1$ and all sufficiently large $n$, then: $$T(n) = \Theta (f(n))$$