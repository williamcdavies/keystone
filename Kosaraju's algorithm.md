---
tags:
  - CS477
---
Kosaraju's algorithm is a linear time algorithm to find the [[Strongly connected components]] of a directed [[Graphs|Graph]]. It makes use of the fact that the [[Transposed graphs|Transpose graph]] has exactly the same strongly connected components as the original graph.

Kosaraju's algorithm can be stated as follows.

```cpp
1. For each vertex u of the graph, mark u as unvisited. Let L be empty.
2. For each vertex u of the graph, Visit(u), where Visit(u) is the recurisve subroutine:
	1. If u is unvisited then:
		1. Mark u as visited.
		2. For each out-neighbor v of u, od Visit(v).
		3. Prepend u to L.
	2. Otherwise do nothing.
3. For each element u of L in order, do Assign(u, u) where Assign(u, root) is the recursive subroutine:
	1. If u has not been assigned to a component then:
		1. Assign u as bolongin to the component whose root is root.
		2. For each in-neighbor v of u, do Assign(v, root).
	2. Otherwise do nothing.
```

In other words, Kosaraju's algorithm involves two main phases:
1. Performing [[Depth-first search]] on the original graph:
	1. We first do a depth-first search on the original graph and record the finish times of nodes (i.e., the time at which the depth-first search finishes exploring a node completely).
2. Perming depth-first search on the [[Transposed graphs|Transpose graph]]:
	1. We then reverse the direction of all edges in the graph to create the transposed graph.
	2. Next, we perform depth-first search on the transposed graph, considering nodes in decreasing order of their finish times recorded in the first phase.
	3. Each depth-first search traversal in this phase will give us once strongly connected component.