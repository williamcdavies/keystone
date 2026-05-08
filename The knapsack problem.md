---
tags:
  - CS477
---
Given a set of items $S$, each with a weight $w_i$ and a value $v_i$, determine which items to include in a collection such that its total weight $\sum{w_i}$ is less than or equal to a given capacity $C$ and its total value $\sum{x_iv_i}$ is maximised.

## The 0-1 Knapsack Problem ([[Dynamic programming]])
Maximise $\sum{x_iv_i}$ subject to
1. $x_i = 0 \text{ or } 1$
2. $\sum{x_iw_i} \leq C$
3. non-negativity

Let `P(i, W)` be the maximum value that can be obtained from items $1$ through $i$ given a knapsack with a remaining capacity of $W$. Then for each item $i < n$:
- `P(i, W) = P(i - 1, W)` if $x_i = 0$.
- `P(i, W) = v_i + P(i - 1, W - w_i)` if $x_i = 1$ and $w_i \leq W$.
Evaluating `P(n, C)` gives an optimal solution to the problem.

## The Fractional Knapsack Problem ([[Greedy algorithms|Greedy programming]])
Maximise $\sum{x_iv_i}$ subject to
1. $x_i \leq 1$
2. $\sum{x_iw_i} \leq W$
3. non-negativity

Let $S$ be ordered such that $\frac{v_1}{w_1} \geq \frac{v_2}{w_2} \geq \dots \geq \frac{v_n}{w_n}$. Then for each item $i < n$
- `x_i = min(1, W / w_i)`.
- `W = W - x_iw_i`.
Where $W$ is the remaining capacity of the knapsack.