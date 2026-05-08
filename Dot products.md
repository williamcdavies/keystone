---
tags:
  - PHYS180
aliases:
  - Dot product
---
The dot product or scalar product is an algebraic operation that takes two equal-length sequences of numbers, and returns a single number. 

Algebraically, the dot product is the sum of the products of the corresponding entries of the two sequences of numbers. Geometrically, it is the product of the [[Euclidean magnitudes]] of the two vectors and the cosine of the angle between them. These definitions are equivalent when using Cartesian coordinates.

## Coordinate Definition
The dot product of two vectors $\text{ a } = [a_1,a_2, \dots ,a_n]$ and $\text{ b } = [b_1,b_2, \dots ,b_n]$, specified with respect to an orthonormal basis, is defined as: 
$$a b = \sum_{i = 1}^n{a_i b_i + a_2 b_2} + \dots + a_n b_n$$

where $n$ is the dimension of the vector space. For instance, in three-dimensional space, the dot product of vectors $[1,3,-5]$ and $[4,-2,-1]$ is:
$$\begin{align}
[1,3,-5] \cdot [4,-2,-1] &= (1 \times 4) + (3 \times -2) + (-5 \times -1) \\\\
&= 4 - 6 + 5 \\\\
&= 3
\end{align}$$

## Geometric Definition
In [[Euclidean space]], the magnitude of euclidean vector $\text{ a }$ is denoted by $\text{ || } \text{ a } \text{ || }$. The dot product of Euclidean vectors $\text{ a }$ and $\text{ b }$ is defined by: 
$$ \text{ a } \cdot \text{ b } = \text{ || } \text{ a } \text{ || } \space \text{ || } \text{ b } \text{ || } \space \cos{ \theta }$$

where $\theta$ is the smallest angle between $\text{ a }$ and $\text{ b }$.

In particular, if vectors $\text{ a }$ and $\text{ b }$ are orthogonal (i.e. their angle is $\frac{ \pi }{2}$ or $90 \degree$), then $cos{ \frac{ \pi }{2} = 0}$, which implies that $\text{ a } \cdot \text{ b } = 0$.

At the other extreme, if they are co-directional, then the angle between them is zero with $\cos{0} = 1$ and $\text{ a } \cdot \text{ b } = \text{ || } \text{ a } \text{ || } \space \text{ || } \text{ b } \text{ || }$, implying that the dot product of a vector $\text{ a }$ with itself is $\text{ a } \cdot \text{ a } = || \text{ a } \text{ || } ^2$, which gives $\text{ || } \text{ a } \text{ || } = \sqrt{a \cdot a}$, the formula for the [[Euclidean length]] of the vector.