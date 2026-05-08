---
tags:
  - CS326
---
Semantic analysis adds semantic information to the parse tree and builds the symbol table. This phase performs semantic checks such as [[Type checking]], [[Object binding]], or [[Definite assignment]], rejecting incorrect programs or issuing warnings. Semantic analysis usually requires a complete parse tree, meaning that this phase logically follows [[Syntax analysis]], and logically precedes the code generations phase.