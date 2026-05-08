---
tags:
  - STAT352
---
Combination is the act of arranging the elements of a [[Sets|Set]] into a sequence such that the elements order does not matter. The number of combinations of a set of size $n$ is given by
$$\frac{n!}{r!(n - r)!}$$

where $r$ is the is the number of elements in a possible [[Subsets|Subset]].

```
# of combinations of subsets of 2 elements from S = {A, B, C}.
```

> [!example]
> $$\begin{align}
\frac{3!}{2!(3-2)!} &= \frac{3 \cdot 2!}{2! \cdot 1!} \\\\
&= 3
\end{align}$$

```
If a bin contains 3 defective widgets and 47 non-defective widgets, how many samples containing 2 defective widgets and 4 non-defective widgets can be made.
```

> [!example]
> $$\begin{align}
N &= C(3, 2) \cdot C(47, 4) \\\\
&= 3 \cdot 178,365 \\\\
&= 535,095
\end{align}$$