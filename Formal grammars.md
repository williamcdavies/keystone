---
tags:
  - CS326
aliases:
  - Formal grammar
---
A formal grammar describes which strings from the alphabets of [[Formal languages]] are valid according to the language's syntax. Formal grammar consist of a set of non-terminal symbols, terminal symbols, production rules, and a designated start symbol. When a parsed sentence is represented by a parse tree, non-terminal symbols are represented by internal nodes and terminal symbols are represented by external nodes. The start symbol is represented by the root of the parse tree.

A formal grammar $G$ is a $4$-tuple $(V, T, S, P)$, consisting of
- a finite set of nonterminals $V$
- a finite set of terminals $T$
- a start symbol $S$
- a finite set of production rules $P$