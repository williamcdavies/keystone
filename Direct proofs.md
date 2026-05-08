---
tags:
  - CS365
---
Direct proofs are [[Proofs]] where a conclusion is logically deduced from an assumed premise through the use of [[Rules of inference]] and previously established truths. Direct proofs are straightforward and typically involve clear steps from the assumption to the conclusion. They exist in contrast to [[Indirect proofs]].

```
Give a direct proof of the theorem "If n is an odd integer, then n^2 is odd."
```

> [!example]
Note that this theorem states , where $P(n)$ is "$n$ is an odd integer" and $Q(n)$ is "$n^2$ is odd." As we have said, we will follow the usual convention in mathematical proofs by showing that $P(n)$ implies $Q(n)$, and not explicitly using universal instantiation. To begin a direct proof of this theorem, we assume that the hypothesis of this conditional statement is true, namely, we assume that $n$ is odd. By the definition of an odd integer, it follows $n = 2k + 1$, where $k$ is some integer. We want to show that $n^2$ is also odd. We can square both sides of the equation $n = 2k + 1$ to obtain a new equation that expresses $n^2$. When we do this, we find that $n^2 = (2k + 1)^2 = 4k^2 + 4k + 1 = 2(2k^2 + 2k) + 1$. By the definition of an odd integer, we can conclude that $n^2$ is an odd integer (it is one more than twice an integer). Consequently, we have proved that if $n$ is an odd integer, then $n^2$ is an odd integer.