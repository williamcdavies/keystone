---
tags:
  - MATH330
aliases:
  - Linear combination
---
A Linear combination is an expression constructed from a set of terms by multiplying each term by a constant and adding the results (e.g. a linear combination of $x$ and $y$ would be any expression of the form $ax + by$, where $a$ and $b$ are constants).

## Euclidean Vectors
Let the field $K$ be the set $\mathbb{R}$ of real numbers, and let the vector space $V$ be the [[Euclidean space]] $\mathbb{R}^3$. Consider the unit vectors $\vec{e}_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$, $\vec{e}_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$, and $\vec{e}_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$. Then any vector in $\mathbb{R}^3$ is a linear combination of $\vec{e}_1$, $\vec{e}_2$, and $\vec{e}_3$.

To see that this is so, take any arbitrary vector $\begin{pmatrix} a_1 \\ a_2 \\ a_3 \end{pmatrix}$ in $\mathbb{R}_3$, and write:
$$\begin{align}
\begin{pmatrix} a_1 \\ a_2 \\ a_3 \end{pmatrix} &= \begin{pmatrix} a_1 \\ 0 \\ 0 \end{pmatrix} + \begin{pmatrix} 0 \\ a_2 \\ 0 \end{pmatrix} + \begin{pmatrix} 0 \\ 0 \\ a_3 \end{pmatrix} \\\\
&= a_1 \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} + a_2 \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} + a_3 \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \\\\
&= a_1 \vec{e}_1 + a_2 \vec{e}_2 + a_3 \vec{e}_3
\end{align}$$