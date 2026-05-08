---
tags:
  - CS477
---
Matrix-chain multiplication is an optimisation problem concerning the most efficient way to multiply a given sequence of matrices (given the sequence $A_1, A_2, \dots, A_n$ of matrices, compute the product: $\prod_{i = 1}^{n}{A_i}$).

```
What is the most efficient way to compute the product of the sequence A_1 (10x100), A_2(100x5), A_3(5x50)?
```

> [!example]
> 1. $((A_1 \cdot A_2) \cdot A_3)$
$A_1 \cdot A_2$ requires $5000$ scalar multiplications
$((A_1 \cdot A_2) \cdot A_3)$ requires $2500$ scalar multiplications 
Total: $7500$ operations
> 2. $(A_1 \cdot (A_2 \cdot A_3))$
$A_2 \cdot A_3$ takes $25000$ operations
$(A_1 \cdot (A_2 \cdot A_3))$ takes $50000$ operations
Total: $75000$ operations
>
$(A_1 \cdot A_2) \cdot A_3$ is computationally more efficient than $A_1 \cdot (A_2 \cdot A_3)$.

The matrix-chain multiplication problem can be solved dynamically by immediately reducing any sequence to the product of two matrices ($A_{1 \dots k} \cdot A_{k + 1 \dots n}$). The same problem can then be solved for each sub-sequence until a base case is reached.