---
tags:
  - CS302
---
Red-black trees are specialised [[Binary search trees]] noted for fast storage and retrieval of ordered information, and a guarantee that operations will complete within a know time. Compared to other [[Self-balancing binary search trees]], the nodes in a red-black tree hold an extra bit called representing "red" or "black" which is used when re-organising the tree to ensure that it is always approximately balanced. A red-black tree with $n$ internal nodes has height at most $2 \log{(n + 1)}$.

## Constraints
1. Every node is either "red" or "black".
2. All NIL nodes are considered "black".
3. A "red" node does not have a "red" child.
4. Every path from a given node to any of its descendent NIL nodes goes through the same number of "black" nodes.
5. If a node $N$ has exactly one child, it must be a "red" child, because if it were "black", its NIL descendants would sit at a different "black" depth than $N$'s NIL child, violating the previous requirement.

## Augmenting Red-Black Trees
Let $f$ be a field that augments a red-black tree. If the contents of $f$ for a node can be computed using only the information in $x$, left($x$), and right($x$) we can maintain the values of $f$ in all nodes during insertion and deletion, without affecting their $O( \log{{n}} )$ running time.