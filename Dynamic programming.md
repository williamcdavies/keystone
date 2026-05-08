---
tags:
  - CS477
---
Dynamic programming is both a mathematical optimisation method and an algorithm paradigm.

In both contexts it refers to simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner.

There are two key attributes that a problem must have in order for dynamic programming to be applicable: optimal substructure and overlapping sub-problems. If a problem can be solved by combing optimal solutions to non-overlapping sub-problems, the strategy is called "divide and conquer" instead.

*Optimal substructure* means that the solution to a given optimisation problem can be obtained by the combination of optimal solutions to its sub-problems. Such optimal substructures are usually described by means of recursion. For example, given a [[Graphs|Graph]] $G = (V, E)$, the shortest path $p$ from a vertex $u$ to a vertex $v$  is truly the shortest path, then it can be split into sub-paths $p_1$ from $u$ to $w$ and $p_2$ from $w$ to $v$ such that these, in turn, are indeed the shortest paths between the corresponding vertices. Hence, one can easily formulate the solution for finding the shortest paths in a recursive manner.

*Overlapping sub-problems* means that the space of sub-problems must be small, that is, any recursive algorithm solving the problem should solve the same sub-problems over and over, rather than generating new sub-problems. For example, consider the recursive formulation for generating the Fibonacci sequence: $F_i = F_{i - 1} + F_{i - 2}$, with the base case $F_1 = F_2 = 1$. Then $F_{43}$ = $F{42} + F_{41}$, and $F_{42} = F_{41} + F_{40}$. Now $F_41$ is being solved in the recursive sub-tress of both $F_{43}$ as well as $F_{42}$. Even though the total number of sub-problems is actually small, we end up solving the same problems over and over if we adopt a naive recursive solution such as this. Dynamic programming takes account of this fact and solves each sub-problem only once.

