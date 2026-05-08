---
tags:
  - EE220
---
The node-voltage method is a method of determining the [[Electric voltage]] between nodes in an electrical circuit in terms of the branch currents.

## Procedure
1. Note all connected wire segments in the circuit. These are the nodes of nodal analysis.
2. Select one node as the ground reference. The choice does not affect the element voltages (but it does affect the nodal voltages) and is just a matter of convention. Choosing the node with the most connections can simplify the analysis. For a circuit of $N$ nodes the number of nodal equations is $N - 1$.
3. Assign a variable for each node whose voltage is unknown. If the voltage is already known, it is not necessary to assign a variable.
4. For each unknown voltage, form an equation based on [[Kirchoff's circuit laws|Kirchoff's current law]] (i.i add together all currents leaving from the node and mark the sum equal to zero). The current between two nodes is equal to the voltage of the node where the current exits minus the voltage of the node where the current enters the node, both divided by the resistance between the two nodes.
5. If there are voltage sources between two unknown voltages, join the two nodes as a supernode. The currents of the two nodes are combined in a single equation and a new equation for the voltages is formed.
6. Solve the system of simultaneous equations for each unknown voltage.