---
tags:
  - CPE400
---
A distance-vector routing protocol determines the best route for data packets based on distance. Distance-vector routing protocols measure the distance by the number of [[Routers]] a packet has to pass, one router counts as one hop.

Distance-vector routing protocols use the [[Bellman-ford algorithm]] to calculate the best route.

```
Given the following network, determine the shortest route from A to D using the distance-vector (distributed Bellman-Ford) algorithm. Let d_B(D) = 3 and d_C(D) = 1.

   A
  / \
1/   \4
B -2- C
5\   /1
  \ /
   D
```

> [!example]
> $$\begin{align}
d_A(D) &= \min_{n \in N(A)}{(c(A, n) + d_n(D))} \\ \space \\
d_A(D) &= \min{(c(A, B) + d_B(D), c(A, C) + d_C(D))} \\ \space \\
d_A(D) &= \min{(1 + 3, 4 + 1)} \\ \space \\
d_A(D) &= \min{(4, 5)} \\ \space \\
d_A(D) &= 4 \\ \space \\
\end{align}$$