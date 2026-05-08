---
tags:
  - CS658
---
The Jaccard index is a statistic used for gauging the [[Similarity measures|Similarity]] and diversity of sample sets.

The Jaccard index measures similarity between finite non-empty sample sets and is defined as the size of the intersection divided by the size of the union of the sample sets:
$$J(A, B) = \frac{ \text{ | } A \cap B \text{ | } }{ \text{ | } A \cup B \text{ | } } = \frac{ \text{ | } A \cap B \text{ | } }{ \text{ | } A \text{ | } + \text{ | } B \text{ | } - \text{ | } A \cap B \text{ | } }$$

Note that by design $0 \leq J(A, B) \leq 1$. If the sets $A$ and $B$ have no elements in common, their intersection is empty, so $\text{ | } A \cap B \text{ | } = 0$ and therefore $J(A, B) = 0$. The other extreme is that the two sets are equal. In that case $A \cap B = A \cup B = A = B$, so then $J(A, B) = 1$.

## Similarity of Asymmetric Binary Attributes
Given two objects, $A$ and $B$, each with $n$ binary attributes, the Jaccard index is a useful measure of the overlap that $A$ and $B$ share with their attributes. Each attribute of $A$ and $B$ can either be $0$ or $1$. The total number of each combination of attributes for both $A$ and $B$ are specified as follows:
- $M_{11}$ represents the total number of attributes where $A$ and $B$ both have a value of $1$.
- $M_{01}$ represents the total number of attributes where the attribute of $A$ is $0$ and the attribute of $B$ is $1$.
- $M_{10}$ represents the total number of attributes where the attribute of $A$ is $1$ and the attribute of $B$ is $0$.
- $M_{00}$ represents the total number of attributes where $A$ and $B$ both have a value of $0$

Each attribute must fall into one of these four categories, meaning that
$$M_{11} + M_{01} + M_{10} + M_{00} = n$$

The Jaccard similarity index, $J$ is given as
$$J = \frac{M_{11}}{M_{01} + M_{10} + M_{11}}$$

The Jaccard distance, $d_J$, is given as
$$d_J = 1 - J$$

## Other Definitions of Tanimoto Distance
Tanimoto distance is often referred to, erroneously, as a synonym for Jaccard distance $1 - T_s$. This function is a proper distance metric. "Tanimoto Distance" is often stated as being a proper distance metric, probably because of its confusion with Jaccard distance.

If Jaccard or Tanimoto similarity is expressed over a bit vector, then it can be written as
$$f(A, B) = \frac{A \cdot B}{ \text{ || } A \text{ || }^2 + \text{ || } B \text{ || }^2 - A \cdot B}$$

where the same calculation is expressed in terms of vector scalar product and magnitude. This representation relies on the fact that, for a bit vector
$$A \cdot B = \sum_i{A_iB_i} = \sum_i{A_i \land B_i}$$

and
$$\text{ || } A \text{ || }^2 = \sum_i{A_i^2} = \sum_i{A_i}$$