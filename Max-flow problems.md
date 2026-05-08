---
tags:
  - MATH487
---
In optimisation theory, maximum flow problems involve finding a feasible flow through a flow network that obtains the maximum possible flow rate.

```
Let G be a directed graph with edges s1 = 8, s2 = 6, 13 = 10, 14 = 2, 22 = 10, 25 = 8, 3t = 5, 4t = 10, and 5t = 4. If the edge weights define the maximum flow transfer from one node to another, what is the maximum flow from source s to sink t?
```
> [!example]
> $$\begin{align}
\text{ max } x_{3t} + x_{4t} + x_{5t} &= Z \\\\
\text{ s.t. } x_{01} &\leq 8 \\\\
x_{02} &\leq 6 \\\\
x_{13} &\leq 10 \\\\
x_{14} &\leq 2 \\\\
x_{23} &\leq 10 \\\\
x_{25} &\leq 8 \\\\
x_{3t} &\leq 5 \\\\
x_{4t} &\leq 10 \\\\
x_{5t} &\leq 4 \\\\
x_{01} &= x_{13} + x_{14} \\\\
x_{02} &= x_{23} + x_{25} \\\\
x_{13} + x_{23} &= x_{3t} \\\\
x_{14} &= x_{4t} \\\\
x_{25} &= x_{5t}
\end{align}$$
>
$x_{01}^* = 5$, $x_{02}^* = 6$, $x_{13}^* = 3$, $x_{14}^* = 2$, $x_{23}^* = 2$, $x_{25}^* = 4$, $x_{3t}^* = 5$, $x_{4t}^* = 2$, $x_{5t}^* = 6$, $Z^* = 11$.