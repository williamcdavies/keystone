---
tags:
  - CPE201
---
Half-adders are computational binary adders that accept two binary digits on its inputs and produce two binary digits on its outputs, a sum bit $\sum$ and a carry bit $C_{ \text{ out } }$. The mathematics performed by a half-adder and all other binary adders follow the rules of [[Binary addition]].

The carry bit $C_{ \text{ out } }$ is only ever $1$ when both inputs ($A$,$B$) are $1$; therefore, $C_{ \text{ out } }$ can be expressed as the $\&$ of the input variables.

The sum bit $\sum$ is only ever $1$ when both inputs ($A$,$B$) are not equal; therefore $\sum$ can be expressed at the $\oplus$ of the input variables.

| $A$ | $B$ | $C_o$ | $\sum$ |
|:---:|:---:|:-----:|:--------:|
|  0  |  0  |   0   |    0     |
|  0  |  1  |   0   |    1     |
|  1  |  0  |   0   |    1     |
|  1  |  1  |   1   |    0     |