---
tags:
  - CS302
aliases:
  - Graph
---
Graphs are [[Abstract data types]] that are meant to implement the undirected graph and directed graph concepts from the field of [[Graph theory]] within [[Mathematics]].

A graph [[Data structures|Data structure]] consists of a finite set of vertices, together with a set of unordered pairs of these vertices for an undirected graph or a set of ordered pairs for a directed graph. These pairs are known as edges, and for a directed graph are also known as arrows or arcs.

## Graph Traversal
[[Breadth-first search]] and [[Depth-first search]] are two closely-related approaches that are used for exploring all of the nodes in a given connected component. Both start with an arbitrary node.

```cpp
Interface:

#ifndef GRAPH_INTERFACE
#define GRAPH_INTERFACE

template <class LabelType>
class GraphInterface
{
	public:
		virtual int getNumVertices() const = 0;
		virtual int getNumEdges() const = 0;
		virtual bool add(LabelType start, LabelType end, int edgeWeight) = 0;
		virtual bool remove(LabelType start, LabelType end) = 0;
		virtual int getEdgeWeight(LabelType start, LabelType end) const = 0;
		virtual void depthFirstTraversal(LabelType start, void visit(LabelType&)) = 0;
		virtual void breadthFirstTraversal(LabelType start, void visis(LabelType&)) = 0;
		virtual ~GraphInterface() { }
};

#endif
```