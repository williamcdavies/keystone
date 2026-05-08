---
tags:
  - CS477
---
Kruskal's algorithm find a minimum spanning forest of an undirected edge-weighted graph. If the graph is connected, it finds the [[Minimum spanning trees|Minimum spanning tree]]. It is a [[Greedy algorithms|Greedy algorithm]] that in each step adds to the forest the lowest-weight edge that will not form a cycle.

The algorithm performs the following steps:
1. Create a forest initially consisting of a separate single-vertex tree for each vertex in the input graph.
2. Sort the graph edges by weight.
3. Loop through the edges of the graph, in ascending sorted order by their weight. For each edge:
	1. Test whether adding the edge to the current forest would create a cycle.
	2. If not, add the edge to the forest combining two trees into a single tree.
