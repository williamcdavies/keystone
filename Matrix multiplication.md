---
tags:
  - MATH330
---
Matrix multiplication is a binary operation that produces a matrix from two matrices. The number of columns in the first matrix must be equal to the number of rows in the second matrix. The resulting matrix known as the matrix product, has the number of rows as the first and the number of columns of the second. 

## Matrix $\times$ Matrix
If $A$ is an $m \times n$ matrix and $B$ is an $n \times p$ matrix,
$$A = \pmatrix{a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn}} , \space B = \pmatrix{b_{11} & b_{12} & \cdots & b_{1p} \\ b_{21} & b_{22} & \cdots & b_{2p} \\ \vdots & \vdots & \ddots & \vdots \\ b_{n1} & b_{n2} & \cdots & b_{np}}$$

the matrix product $C = AB$ is defined to be the $m \times p$ matrix
$$C = \pmatrix{c_{11} & c_{12} & \cdots & c_{1p} \\ c_{21} & c_{22} & \cdots & c_{2p} \\ \vdots & \vdots & \ddots & \vdots \\ c_{m1} & c_{m2} & \cdots & c_{mp}}$$

such that
$$c_{ij} = a_{i1}b_{1j} + a_{i2}b_{2j} + \dots + a_{in}b_{nj} = \sum_{k = 1}^n{a_{ik}b_{kj}}$$

for $i = 1$ through $m$ and $j = 1$ through $p$.

In other words $c_{ij}$ is the [[Dot products|Dot product]] of the $i$th row of $A$ and the $j$th column of $B$.

## Matrix $\times$ Vector
A vector $x$ of length $n$ can be viewed as a column vector, corresponding to an $n \times 1$ matrix $X$ whose entries are given by $X_{i1} = x_i$. If $A$ is an $m \times n$ matrix, the matrix-times-vector product denoted by $Ax$ is then the vector $y$ that, viewed as a column vector, is equal to the $m \times 1$ matrix $AX$. In index notation, this amounts to:
$$y_i = \sum_{j = 1}^n{a_{ij}x_j}$$

## Vector $\times$ Matrix
Similarly, a vector $x$ of length $n$ can be viewed as a row vector, corresponding to a $1 \times n$ matrix. To make it clear that a row vector is meant, it is customary in this context to represent it as the transpose of a column vector; thus, one will see notations such as $x^TA$. The identity $x^TA = (A^Tx)^T$ holds. In index notation, if $A$ is an $n \times p$ matrix, $x^TA = y^T$ amounts to:
$$y_k = \sum_{j = 1}^n{x_ja_{jk}}$$