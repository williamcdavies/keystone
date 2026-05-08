---
tags:
  - MATH330
---
Laplace expansion, or cofactor expansion, is an expression of the [[Determinants|Determinant]] of an $n \times n$ matrix $B$ as a weighted sum of minors, which are the determinants of some $(n - 1) \times (n - 1)$ sub-matrices of $B$. Specifically, for every $i$, the Laplace expansion along the $i$th row is the equality
$$\det{(B)} = \sum_{j = 1}^n{(-1)^{i + j}b_{i,j}m_{i,j}}$$

where $b_{i,j}$ is the entry of the $i$th row and the $j$th column of $B$, and $m_{i,j}$ is the determinant of the sub-matrix by removing the $i$th row and the $j$th column of $B$. Similarly, the Laplace expansion along the $j$th column is the equality
$$\det{(B)} = \sum_{i = 1}^n{(-1)^{i + j}b_{i,j}m_{i,j}}$$