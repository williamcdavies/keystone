---
tags:
  - CS477
---
Big O is a notation used to describe the "computational complexity" of an [[Algorithms|Algorithm]]. The computational complexity of an algorithm is split into two parts: time complexity and space complexity. The time complexity of an algorithm is the amount of time the algorithm needs to run relative to the input size. The space complexity of an algorithm is the amount of memory used by the algorithm relative to the input size.

Consider functions $f(n)$ and $g(n)$ such that $0 \leq f(n) \leq c \cdot g(n)$ for all $n \geq n_0$, where $c$ and $n_0$ are positive constants. This relationship can be expressed in Big-O notation as $f(n) = O(g(n))$. $O(g(n))$ can be understood as the set of functions with a growth rate equal to or less than $g(n)$.

## Rules
1. Ignore constants. That means $O(8n) = O(n) = O( \frac{n}{500} )$. Why do we do this? Imagine you had two algorithms. Algorithm $A$ uses $~n$ operations and algorithm $B$ uses $~5n$ operations. We don't care that algorithm $B$ is $$