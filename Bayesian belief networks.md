---
tags:
  - CS658
---
A Bayesian belief network is a probabilistic graphical model that represents a set of variables and their conditional dependencies via a directed acyclic graph (DAG. 

## Graphical Model
Formally, Bayesian networks are directed acyclic graphs (DAGs) whose nodes represent variables in the Bayesian sense: they may be observable quantities, latent variables, unknown parameters, or hypotheses. Each edge represents a direct conditional dependency. Any pair of nodes that are not connected (i.e. no path connects one node to the other) represent variables that are conditionally independent of each other. Each node is associated with a probability function that takes, as input, a particular set of values for the node's parent variables, and gives (as output) the probability (or probability distribution, if applicable) of the variable represented by the node. For example, if $m$ parent nodes represent $m$ Boolean variables, then the probability function could be represented by a table of $2^m$ entries, one entry for each of the $2^m$ possible parent combinations. Similar ideas may be applied to undirected, and possibly cyclic, graphs such as Markov networks.