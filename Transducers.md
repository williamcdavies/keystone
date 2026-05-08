---
tags:
  - CS456
---
```
Determine a transducer for the the language L = \{ f(x) = 2x \}.
```
> [!example] 
> $$\begin{align}
M &= (Q, \Sigma, \Gamma, \delta, q_0, B, F) \\ \space \\
&= ( \{ q_i, q_x, q_0, q_1, q_2, q_3 \}, \{ 1 \}, \{ 1, x, \# \}, \delta, q_i, \#, \{ q_0 \} ) \text{ | } \\ \space \\
\delta &= ( \\ \space \\
&(q_i, 1, 1, L, q_i) \\ \space \\
&(q_i, \#, \#, R, q_x) \\ \space \\
&(q_x, 1, x, R, q_x) \\ \space \\
&(q_x, \#, \#, L, q_0) \\ \space \\
&(q_0, x, x, L, q_0) \\ \space \\
&(q_0, \#, \#, R, q_1) \\ \space \\
&(q_1, x, \#, R, q_2) \\ \space \\
&(q_2, x, x, R, q_2) \\ \space \\
&(q_2, \#, 1, R, q_3) \\ \space \\
&(q_3, \#, 1, R, q_0) \\ \space \\
)
\end{align}$$
