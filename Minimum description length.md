---
tags:
  - CS658
---
Minimum Description Length (MDL) is a model selection principle where the shortest description of the data is the best model. MDL methods learn through a data compression perspective and are sometimes described as mathematical applications of [[Occam's razor]].

```
Consider two decision trees, T1 and T2, generated from a dataset containing 16 binary attributes and classes C1, C2, and C3.

T1 has 2 internal nodes and 3 leaf nodes.

T2 has 4internal nodes and 5 leaf nodes.

1. Calculate the cost of each internal node
2. Calculate the cost of each leaf node
3. Calculate the overall cost of T1
4. Calculate the overall cost of T2
```

> [!example]
1. The cost of each internal node is $\lceil \log_2{(m)} \rceil = \lceil \log_2{16} \rceil = 4$.
2. The cost of each leaf node is $\lceil \log_2{(k)} \rceil = \lceil \log_2{3} \rceil = 2$.
3. The overall cost of $T_1$ is $(2 \cdot 4 + 3 \cdot 2) + $