---
tags:
  - CS456
aliases:
  - Context-free grammar
---
A context-free grammar $G$ is defined by the $4$-tuple $G = (V, \Sigma, R, S)$, where
1. $V$ is a finite set; each element $v \in V$ is called a nonterminal character or a variable. Each variable represents a different type of phrase or clause in the sentence. Variables are also sometimes called syntactic categories. Each variable defines a sub-language of the language defined by $G$.
2. $\Sigma$ is a finite set of terminals, disjoint from $V$, which make up the actual content of the sentence. The set of terminals is the alphabet of the language defined by the grammar $G$.
3. $R$ is a finite relation in $V \times (V \cup \Sigma )^*$. The members of $R$ are called productions of the grammar.
4. $S$ is the start symbol, used to represent the whole sentence. It must be an element of $V$.