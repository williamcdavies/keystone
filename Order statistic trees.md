---
tags:
  - CS477
---
An order statistic tree is a variant of the binary search tree that supports two additional operations beyond insertion, lookup, and deletion:
- Select($i$) - find the $i$-th smallest element stored in the tree
- Rank($x$) - find the rank of element $x$ in the tree, i.e. its index in the sorted list of elements of the tree

Both operations can be performed in $O( \log{(n)} )$ worst case time when a self-balancing tree is used as the base data structure.