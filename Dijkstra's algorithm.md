---
tags:
  - CS302
---
Dijkstra's algorithm is an algorithm for finding the shortest paths between nodes in a weighted [[Graphs|Graph]]. The algorithm uses a min-priority [[Queues|Queue]] [[Data structures|Data structure]] for selecting the shortest paths known so far. Dijkstra's algorithm uses $O(n^2)$ operations.

Dijkstra's algorithm begins by labeling $a$ with $0$ and the other vertices with $\infty$ ($L_0 (a) = 0$ and $L_0 (v) = \infty$). These labels are the lengths of shortest paths for $a$ to the vertices, where the paths contain only the vertex $a$ (Because no path from $a$ to a vertex difference from $a$ exists, $\infty$ is the length of a shortest path between $a$ and this vertex.).

Dijkstra's algorithm proceeds by forming a distinguished set of vertices. Let $S_k$ denote this set after $k$ iterations of the labeling procedure. We being with $S_0 = \emptyset$. The set $S_k$ is formed from $S_{k-1}$ by adding a vertex $u$ not in $S_{k-1}$ with the smallest label.

Once $u$ is added to $S_k$, we update the labels of all vertices not in $S_k$, so that $L_k (v)$, the label of the vertex $v$ at the $k$th stage, is the length of a shortest path from $a$ to $v$ that contains vertices only in $S_K$ (that is, vertices that were already in the distinguished set together with $u$). Note that the way the vertex $u$ is chosen at each step is an optimal choice at each step, making this a greedy algorithm.