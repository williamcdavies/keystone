---
tags:
  - CS658
aliases:
  - Measure of similarity
  - Similarity
---
A similarity measure is a real-valued function that quantifies the similarity between two objects. Although no single definition of a similarity exists, usually such measures are in some sense the inverse of distance metrics: they take on large values for similar objects and either zero or a negative value for very dissimilar objects. Though, in more broad terms, a similarity function may also satisfy metric axioms.

## Similarity/Dissimilarity for Simple Attributes
Let $p$ and $q$ be two distinct data objects. Then:

|    attribute type |                                                                             dissimilarity |                                                                                similarity |
| -----------------:| -----------------------------------------------------------------------------------------:| -----------------------------------------------------------------------------------------:|
|           nominal | $$d = \begin{cases} 0 \text{ if } p = q \\ \space \\ 1 \text{ if } p \neq q \end{cases}$$ | $$s = \begin{cases} 1 \text{ if } p = q \\ \space \\ 0 \text{ if } p \neq q \end{cases}$$ |
|           ordinal |                                               $$d = \frac{ \lvert p - q \rvert }{n - 1}$$ |                                          $$s = 1 -  \frac{ \lvert p - q \rvert }{n - 1}$$ |
| interval or ratio |                                                               $$d = \lvert p - q \rvert$$ | $$s = -d$$, $$s = \frac{1}{1 + d}$$, $$s = 1 - \frac{d - \min{d} }{ \max{d} - \min{d} }$$ |

## General Approach for Combining Similarities
1. For the $k^{ \text{ th } }$ attribute, compute a similarity, $s_k$, in the range $[0, 1]$.
2. Define an indicator variable, $\delta_k$, for the $k^{ \text{ th } }$ attribute as follows: $$\delta_k = \begin{cases} 0 \text{ if the } k^{ \text{ th } } \text{ attribute is a binary asymmetric attribute and both objects have a value of } 0 \text{ , or if one of the objects has a missing value for the } k^{ \text{ th } } \text{ attribute } \\ \space \\ 1 \text{ otherwise } \end{cases}$$
3. Compute the overall similarity between the two objects using the following formula: $$\text{ similarity } (p, q) = \frac{ \sum_{k = 1}^n { \delta_k s_k} }{ \sum_{k = 1}^n { \delta_k } }$$

### Using Weights to Combine Similarities
$$\text{ similarity } (p, q) = \frac{ \sum_{k = 1}^n { w_k \delta_k s_k} }{ \sum_{k = 1}^n { \delta_k } }$$
$$\text{ distance } (p, q) = \left( \sum_{k = 1}^n {w_k \text{ | } p_k - q_k \text{ | }^r } \right)^{ \frac{1}{r} }$$

for weights $w_k \rightarrow [0, 1]$.