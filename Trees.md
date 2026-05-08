---
tags:
  - CS302
aliases:
  - Tree
---
Trees are [[Abstract data types]] that represent a hierarchical tree structure with sets of connected [[Nodes]]. Each node in a tree can be connected to many children, but may only be connected to one parent. These constraints allow each child to be treated as the root node of its own subtree, making [[Recursion]] a useful technique for tree traversal. In [[Graph theory]], a tree is defined as a connected [[Graphs|Graph]] that contains no simple circuits.

## Terminology
Each node in a tree has zero or more child nodes, which are placed below the parent node in the tree. A node might have many ancestor nodes, such as the parent's parent. Child nodes with the same parent are sibling nodes.

An internal node (also known as an inner node, inode, or branch node) is any node of a tree that has child nodes. An external node (also known as an outer node, leaf node, or terminal node) is any node that does not have child nodes.

The height of a node is the length of the longest edge path to a leaf from that node. The height of the root is the height of the tree. The depth of a node is the length of the path to its root (i.e., its root path). Therefore, root nodes have depth 0, and leaf nodes have a height 0. An empty tree has height -1.

```cpp
Interface:

#ifndef TREE_INTERFACE
#define TREE_INTERFACE

template <class ItemType>
class TreeInterface
{
	public:
		virtual bool isEmpty() const = 0;
		virtual int getHeight() const = 0;
		virtual int getNummberOfNodes() const = 0;
		virtual ItemType getRootData() const = 0;
		virtual bool add(const ItemType& anEntry) = 0;
		virtaul bool remove(const ItemType& anEntry) = 0;
		virtual void clear() = 0;
		virtual bool contains(const ItemType& anEntry) const = 0;
		virtual ~TreeInterface() { }
};

#endif
```