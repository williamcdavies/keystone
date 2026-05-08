---
tags:
  - CS658
---
The pessimistic error estimate of a decision tree $T$, $e_g(T)$, can be computed as follows:
$$e_g(T) = \frac{ \sum_{i = 1}^k{[e(t_i) + \Omega (t_i) ]} }{ \sum_{i = 1}^k{n(t_i)} } = \frac{e(T) + \Omega (T)}{N_t}$$

where $k$ is the number of leaf nodes, $e(T)$ is the overall training error of the decision tree, $N_t$ is the number of training records, and $\Omega(t_i)$ is the penalty term associated with each node $t_i$.