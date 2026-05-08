---
tags:
  - CS477
---
A topological sort of a directed [[Graphs|Graph]] is a linear ordering of its. vertices such that for every directed edge $(u, v)$ from vertex $u$ to vertex $v$, $u$ comes before $v$ in the ordering. For instance, the vertices of the graph may represent tasks.

An algorithm for topological sorting is based on [[Depth-first search]]. The algorithm loops through each node of the graph, in arbitrary order, initiating a depth-first search that terminates when it hits any node that has already been visited since the beginning of the topological sort or the node has no outgoing edges.

```cpp
L <- Empty list that will contain the sorted nodes
while exists nodes without a permanent mark do
	select an unmarked node n
	visit(n)

function visit(node n)
	if n has a permanent mark then
		return
	if n has a temporary mark then
		stop (graph has at least one cycle)

	mark n with a temporary mark

	for each node m with an edge from n to m do
		visit(m)

	mark n with a permanent mark
	add n to head of L
```

Each node $n$ gets prepended to the output list $L$ only after considering all other nodes that depend on $n$ (all descendants of $n$ in the graph). Specifically, when the algorithm adds node $n$, we are guaranteed that all nodes that depend on $n$ are already in the output list $L$: they were added to $L$ either by the recursive call to visit() that ended before the call to visit $n$, or by a call to visit() that started even before the call to visit $n$. Since each edge and node is visited once, the algorithm runs in linear time (that is, $\Theta (V + E)$).