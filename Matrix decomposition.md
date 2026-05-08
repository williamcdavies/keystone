---
tags:
  - MATH330
---
A matrix decomposition is a factorisation of a matrix into a product of matrices.

When solving a system of linear equations $Ax = b$, the matrix $A$ can be decomposed via the [[LU decomposition]]. The $LU$ decomposition factorises a matrix into a lower triangular matrix $L$ and an upper triangular matrix $U$. The systems $L(Ux) = b$ and $Ux = L^{-1}b$ require fewer additions and multiplication to solve, compared with the original system $Ax = b$, though one might require significantly more digits in inexact arithmetic such as floating point.