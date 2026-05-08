---
tags:
  - CS477
---
An interval tree is a [[Trees|Tree]] data structure to hold intervals, Specifically it allows one to efficiently find all intervals that overlap with any given interval or point. It is often used for windowing queries, for instance, to find all roads on a computerised map inside a rectangular viewport, or to find all visible elements inside a three-dimensional scene.

## Interval Trichotomy
Any two intervals $i$ and $j$ satisfy the interval trichotomy: exaclty one of the following three properties holds:
- $i$ and $j$ overlap
- $i$ is to the left of $j$ (high($i$) $<$ low($j$))
- $i$ is to the right of $j$ (high($j$) $<$ low($i$))