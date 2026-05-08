---
tags:
  - EE220
---
The Bellman-Ford algorithm is an algorithm that computes shortest paths from a single source vertex to all other vertices in a weighted digraph. It is slower than [[Dijkstra's algorithm]] for the same problem, but more versatile, as it is capable of handling graphs in which some of the edge weights are negative numbers.

Like Dijkstra's algorithm, Bellman-Ford proceeds by relaxation, in which approximations to the correct distance are replaced by better ones until they  reach the solution. In both algorithms, the approximate distance to each vertex is always an overestimate of the true distance, and is replaced by the minimum of its old value and the length of a newly found path.

However, Dijkstra's algorithm uses a priority [[Queues|Queue]] to greedily select the closest vertex that has not yet been processed, and performs this relaxation on all of its outgoing edges; by contrast, the Bellman-Ford algorithm simply relaxes all the edges, and does this $\text{ | } V \text{ | } - 1$ times, where $\text{ | } V \text{ | }$ is the number of vertices in the graph.

In each of these repetitions, the number of vertices with correctly calculated distances grows, from which it follows that eventually all vertices will have their correct distances. This method allows the Bellman-Ford algorithm to be applied to a wider class of inputs than Dijkstra's algorithm. The intermediate answers depend on the orders of edges relaxed, but the final answer remains the same.

Bellman-Ford runs in $O( \text{ | } V \text{ | } \cdot \text{ | } E \text{ | } )$ time, where $\text{ | } V \text{ | }$ and $\text{ | } E \text{ | }$ are the number of vertices and edges respectively.

```python
function BellmanFord(list vertices, list edges, vertex source) is
	// This implementation takes in a graph, represented as lists of vertices (represented as integers [0 .. n - 1]) and edges, and fills two arrays (distance and predecessor) holding the shortest path from the source to each vertex

	distance := list of size n
	predecessor := list of size n
	// Step 1: initialise graph
	for each vertex in vertices do
		// Initialise the distance to all vertices to infinity
		distance[v] := inf
		// And having a null predecessor
		predecessor[v] := null
	
	// The distance from the source to itself is zero
	distance[source] := 0

	// Step 2: relax edges repeatedly
	repeat |V| - 1 times:
		for each edge (u, v) with weight w in edges do
			if distance[u] + w < distance[v] then
				distance[v] := distance[u] + w
				predecessor[v] := u

	// Step 3: check for negative-weight cycles
	for each edge (u, v) with weight w in edges do
		if distance[u] + w < distance[v] then
			predecessor[v] := u
			// A negative cycle exists; find a vertex on the cycle
			visited := list of size n initialised with false
			visited[v] := true
			while not visited[u] do
				visited[u] := true
				u := predecessor[u]
			// u is a vertex in a negative cycle, find teh cycle itself
			ncycle := [u]
			v := predecessor[u]
			while v != u do
				nycle := concatenate([v], nycle)
				v := predecessor[v]
			error "Graph contains a negative-weight cycle", ncycle
	return distance, predecessor
```

```cpp
1. INITIALISE-SINGLE-SOURCE(V, s)
2. for i <- 1 to |V| - 1
	1. do for each edge (u, v) in E
		1. do RELAX(u, v, w)
```