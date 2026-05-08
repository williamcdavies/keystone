---
tags:
  - CS658
---
Cosine similarity is a [[Similarity measures|Measure of similarity]] between two non zero vectors defined in an inner product space. Cosine similarity is the cosine of the angle between the vectors; that is, it is the [[Dot products|Dot product]] of the vectors divided by the product of their lengths. It follows that cosine similarity does not depend on the magnitudes of the vectors, but only their angle. The cosine similarity belongs to the interval $[-1, +1]$. For example, two proportional vectors have a similarity of $0$, and two opposite vectors have a similarity of $-1$. In some contexts, the component values of the vectors cannot be negative, in which case the cosine similarity is bounded in $[0, 1]$.

The cosine of two non-zero vectors can be derived by using the Euclidean dot product formula:
$$\vec{A} \cdot \vec{B} = \text{ || } \vec{A} \text{ || } \text{ || } \vec{B} \text{ || } \cos{ \theta }$$

Given two $n$-dimensional vectors of attributes, $\vec{A}$ and $\vec{B}$, the cosine similarity, $\cos{ \theta }$, is represented using a dot product and magnitude as
$$\begin{align}
\text{ cosine similarity } &= S_C(A, B) \\ \space \\
&:= \cos{ \theta } \\ \space \\
&= \frac{ \vec{A} \cdot \vec{B} }{ \text{ || } \vec{A} \text{ || } \text{ || } \vec{B} \text{ || } } \\ \space \\
&= \frac{ \sum_{i = 1}^n{A_iB_i} }{ \sqrt{ \sum_{i = 1}^n{A_i^2} } \cdot \sqrt{ \sum_{i = 1}^n{B_i^2} } }
\end{align}$$