---
tags:
  - CPE201
aliases:
  - Full-adder
---
Full-adders are computational binary adders that accept three binary digits $A,B,C_{ \text{ in } }$ on its inputs and produce two binary digits on its outputs, a sum bit $\sum$ and a carry bit $C_{ \text{ out } }$. 

The sum bit $\sum$ is modelled by the equation: 
$$\sum = (A \oplus B) \oplus C_i$$

The carry bit $C_{ \text{out} }$ is modelled by the equation: 
$$C_{ \text{ out } } = AB + (A \oplus B)C_{ \text{ in } }$$

| $A$ | $B$ | $C_i$ | $C_o$ | $\sum$ |
|:---:|:---:|:-----:|:-----:|:--------:|
|  0  |  0  |   0   |   0   |    0     |
|  0  |  0  |   1   |   0   |    1     |
|  0  |  1  |   0   |   0   |    1     |
|  0  |  1  |   1   |   1   |    0     |
|  1  |  0  |   0   |   0   |    1     |
|  1  |  0  |   1   |   1   |    0     |
|  1  |  1  |   0   |   1   |    0     |
|  1  |  1  |   1   |   1   |    1     |
