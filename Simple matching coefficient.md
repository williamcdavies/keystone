---
tags:
  - CS658
---
The simple matching coefficient (SMC) is a statistic used for comparing the [[Similarity measures|Similarity]] and diversity of sample sets.

Given two objects, $A$ and $B$, each with $n$ binary attributes, SMC is defined as:
$$\text{ SMC } = \frac{M_{00} + M_{11}}{M_{00} + M_{11} + M_{01} + M_{10}}$$

where
- $M_{11}$ represents the total number of attributes where $A$ and $B$ both have a value of $1$.
- $M_{01}$ represents the total number of attributes where the attribute of $A$ is $0$ and the attribute of $B$ is $1$.
- $M_{10}$ represents the total number of attributes where the attribute of $A$ is $1$ and the attribute of $B$ is $0$.
- $M_{00}$ represents the total number of attributes where $A$ and $B$ both have a value of $0$