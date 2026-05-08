---
tags:
  - CS302
---
Breadth-first search is an algorithm for searching or traversing [[Trees]] or [[Graphs]] for a node that satisfies a given property. It starts with an arbitrary node and explores all nodes at the present depth prior to moving on to the nodes at the next depth. Extra memory, usually [[Queues]], are needed to keep track of the child nodes that were encountered but not yet explored.

In contrast, [[Depth-first search]], which explores the node branch as far as possible before backtracking and expanding other nodes, may get lost in an infinite branch and never make it to the target node.