---
tags:
  - EE220
---
Consider a system of $n$ linear equations for $n$ unknowns, represented in matrix multiplication form as follows:
$$A \vec{x} = \vec{b}$$

where the $n \times n$ matrix $A$ has a nonzero [[Determinants|Determinant]], and the vector $\vec{x} = (x_1, \dots , x_n)^T$ is the column vector of the variables. Then the theorem states that in this case the system as a unique solution, whose individual values for the unknown are given by:
$$x_i = \frac{ \det{A_i} }{ \det{A} } \qquad i = 1, \dots , n$$

where $A_i$ is the matrix formed by replacing the $i$-th column of $A$ by the column vector $\vec{b}$.