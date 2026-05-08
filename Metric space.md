---
tags:
  - CS658
---
A metric space is a set together with a notion of distance between its elements, usually called points. The distance is measured by a function called a metric or distance function.

Formally, a metric space is an ordered pair $(M, d)$ where $M$ is a set and $d$ is a metric on $M$, i.e, a function
$$d: M \times M \rightarrow \mathbb{R}$$

satisfying the following axioms for all points $x, y, z \in M$:
1. The distance from a point to itself is zero: $$d(x, x) = 0$$
2. The distance between two distinct points is always positive (positivity): $$\text{ If } x \neq y, \text{ then } d(x, y) > 0$$
3. The distance from $x$ to $y$ is always the same as the distance from $y$ to $x$ (symmetry): $$d(x, y) = d(y, x)$$
4. The triangle inequality holds: $$d(x, z) \leq d(x, y) + d(y, z)$$ This is a natural property of both physical and metaphorical notions of distance: you can arrive at $z$ from $x$ by taking a detour through $y$, but his will not make your journey any shorter than the direct path.