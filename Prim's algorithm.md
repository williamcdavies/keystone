---
tags:
  - CS302
---
Prim's algorithm is a greedy algorithm that finds a minimum spanning [[Trees|Tree]] for a weighted undirected [[Graphs|Graph]]. This means it find a [[Subsets|Subset]] of edges that forms a tree that includes every vertex, where the total weight of all the edges in the tree is minimised. The algorithm operates by building this tree one vertex at a time, from an arbitrary staring vertex, at each step adding the cheapest possible connection from the tree to another vertex.