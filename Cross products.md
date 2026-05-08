---
tags:
  - PHYS180
aliases:
  - Cross product
---
The cross product or vector product is a binary operation on two vectors in a three-dimensional [[Euclidean space]], and is denoted by the symbol $\times$. Given two linearly independent vectors $a$ and $b$, the cross product, $a \times b$, is a vector that is perpendicular to both $a$ and $b$, and thus normal to the plane containing them. It should not be confused with the [[Dot products|Dot product]].

If two vectors are parallel or are anti-parallel, or if either one has zero length, then their cross product is zero.

The cross product is [[Anti-commutative]] ($a \times b = -(b \times a)$) and is defined by the formula:
$$a \times b = \text{ || } a \text{ || } \space \text{ || } b \text{ || } \space \sin{ \theta } \space n$$

where:
- $\theta$ is the angle between $a$ and $b$ in the [[Euclidean plane]] containing them,
- $\text{ || } a \text{ || }$ and $\text{ || } b \text{ || }$ are the magnitudes of vectors $a$ and $b$, and
- $n$ is a unit vector perpendicular to the Euclidean plane containing $a$ and $b$, with direction such that the ordered set $a, b, n$ is positively oriented.

## Computing
If ($i, j, k$) is a positively oriented orthonormal basis, the basis vectors satisfy the following equalities: 
$$\begin{align}
i \times j &= k \\\\
j \times k &= i \\\\
k \times i &= j
\end{align}$$

which imply, by the anti-commutativity of the cross product, that: 
$$\begin{align}
j \times i &= -k \\\\
k \times j &= -i \\\\
i \times k &= -j
\end{align}$$

Since any vector can be defined the sum of three orthogonal components parallel to the standard basis vectors:
$$\begin{align}
a &= a_1 i + a_2 j + a_3 k \\\\
b &= b_1 i + b_2 j + b_3 k
\end{align}$$

Their cross product can be expanded:
$$\begin{align}
a \times b &= (a_1 i + a_2 j + a_3) \times (b_1 i + b_2 j + b_3) \\\\
&= a_1 b_1 (i \times i) + a_1 b_2 (i \times j) + a_1 b_3 (i \times k) + \\\\
& a_2 b_1 (j \times i) + a_2 b_2 (j \times j) + a_2 b_3 (j \times k) + \\\\
& a_3 b_1 (k \times i) + a_3 b_2 (k \times j) + a_3 b_3 (k \times k)
\end{align}$$

## Matrix Notation
The cross product can also be expressed as the formal determinant:
$$a \times b =
\begin{bmatrix} 
i & j & k \\
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3 \\
\end{bmatrix}$$

This determinant can be computed using [[Laplace expansion]].



