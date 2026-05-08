---
tags:
  - CS365
---
Indirect proofs, or proofs by contradiction, are [[Proofs]] where a conclusion is logically deduced from the negation of an assumed premise through the use of [[Rules of inference]] and previously established truths.

```
Prove that if n = ab, where a and b are positive integers, then a <= sqrt{n} or b <= sqrt{n}.
```

> [!example]
Because there is no obvious way of showing that $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$ directly from the equation $n = ab$, where $a$ and $b$ are positive integers, we attempt a proof by contraposition.
>
The first step in a proof by contraposition is to assume that the conclusion of the conditional statement "If $n = ab$, where $a$ and $b$ are positive integers, then $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$" is false. That is, we assume that the statement $(a \leq \sqrt{n} ) \lor (b \leq \sqrt{n} )$ is false. Using the meaning of disjunction together with De Morgan's law, we see that this implies that both $a \leq \sqrt{n}$ and $b \leq \sqrt{n}$ are false. This implies that $a > \sqrt{n}$ and $b > \sqrt{n}$. We can multiply these inequalities together (using the fact that if $0 < s < t$ and $0 < u < v$, then $su < tv$) to obtain $ab > \sqrt{n} \cdot \sqrt{n} = n$. This shows that $ab \neq n$, which contradicts the statement $n = ab$.
>
Because the negation of the conclusion of the conditional statement implies that the hypothesis is false, the original conditional statement is true. our proof by contraposition succeeded; we have proved that if $n = ab$ where $a$ and $b$ are positive integers, then $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$.