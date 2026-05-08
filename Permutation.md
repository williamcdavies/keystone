---
tags:
  - STAT352
---
Permutation is the act of arranging the elements of a [[Sets|Set]] into a sequence. The number of permutations of a set of size $n$ is given by
$$\frac{n!}{(n - k)!}$$

where $k$ is the is the number of elements in a possible [[Subsets|Subset]].

```
# of permutations of subsets of 2 elements from S = {A, B, C}.
```

> [!example]
> $$\begin{align}
\frac{3!}{(3-2)!} &= \frac{3!}{1!} \\\\
&= 3! \\\\
&= 6
\end{align}$$

```
# of numberals written from S = {3, 3, 4, 4, 4, 5}.
```

> [!example]
> $$\begin{align}
\frac{6!}{2! \cdot 3! \cdot 1!} &= \frac{6 \cdot 5 \cdot 4 \cdot 3!}{2! \cdot 3!} \\\\
&= \frac{6 \cdot 5 \cdot 4}{2!} \\\\
&= \frac{6 \cdot 5 \cdot 4}{2} \\\\
&= 3 \cdot 5 \cdot 4 \\\\
&= 60
\end{align}$$