---
tags:
  - CS477
aliases:
  - Minimum spanning tree
---
A minimum spanning tree is a subset of the edges of a connected, edge-weighted undirected [[Graphs|Graph]] that connects all the vertices together, without any cycles and with the minimum possible total edge weight.

## Properties

### Possible multiplicity
If there are $n$ vertices in the graph, then each spanning tree has $n - 1$ edges.

There may be several minimum spanning trees of the same weight; in particular, if all the edge weights of a given graph are the same, then every spanning tree of that graph is minimum.

### Uniqueness 
If each edge has a distinct weight then there will be only one, unique minimum spanning tree.

### Cycle property
For any cycle $C$ in the graph, if the weight of an edge $e$ of $C$ is larger than any of the individual weights of all other edges of $C$, then this edge cannot belong to a minimum spanning tree.

### Cut property
For any cut $C$ of the graph, if the weight of an edge $e$ in the cut-set of $C$ is strictly smaller than the weights of all other edges of the cut-set of $C$, then this edge belongs to all minimum spanning trees of the graph.

### Contraction
If $T$ is a tree of minimum spanning tree edges, then we can contract $T$ into a single vertex while maintaining the invariant that the minimum spanning tree of the contracted graph plus $T$ gives the minimum spanning tree for the graph before contraction.