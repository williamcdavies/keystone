---
tags:
  - CS477
---
Big O is a notation used to describe the "computational complexity" of an [[Algorithms|Algorithm]]. The computational complexity of an algorithm is split into two parts: time complexity and space complexity. The time complexity of an algorithm is the amount of time the algorithm needs to run relative to the input size. The space complexity of an algorithm is the amount of memory used by the algorithm relative to the input size.

Consider functions $f(n)$ and $g(n)$ such that $0 \leq f(n) \leq c \cdot g(n)$ for all $n \geq n_0$, where $c$ and $n_0$ are positive constants. This relationship can be expressed in Big-O notation as $f(n) = O(g(n))$. $O(g(n))$ can be understood as the set of functions with a growth rate equal to or less than $g(n)$.

## Rules
1. First, ignore constants. That means $O(8n) = O(n)$.
2. Second, consider the complexity as the variables tend to infinity. That means $O(2^n + n^2 - 500n) = O(2^n)$.

> [!note]
> The best complexity possible is $O(1)$, called "constant time" or "constant space". It means that the algorithm always uses the same amount of resources, regardless of the input. 
> 
> Note that a constant time complexity doesn't necessarily mean that the algorithm is fast (for example $O( \infty ) = O(1)$), it just means that its runtime is independent of the input size.

When talking about complexity, there are normally three cases:
1. Best case
2. Average case
3. Worst case

For most algorithms, all three of these will be equal, but some algorithms will have them differ. If you have to choose only one to represent the algorithm's time or space complexity, never choose the best case scenario. It is most correct to use the worst case scenario, but you should be able to talk about the difference between the cases.

## Analysing time complexity
Consider:

```
for (int num: arr) {
	print(num)
}
```

This algorithm has a time complexity of $O(n)$. In each for loop iteration, we are performing a print, which costs $O(1)$. The for loop iterates $n$ times, which gives a time complexity of $O(1 \cdot n) = O(n)$.