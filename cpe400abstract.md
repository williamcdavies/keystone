---
tags:
  - CPE400
---
## Team Members:
- William Chuter-Davies

## Project Title:
- Network Simulation Shell

## Project Abstract:
This purpose of this project is to provide command-line tools for implementing and evaluating virtual networks under simulated network constraints (i.e., packet loss/delay, nodal/network failure, etc.).

### Implementation Tools
Users will be able to implement virtual networks using a set of provided shell commands. The ability to define custom shell commands may also be provided. The user will be provided with the following commands (at least):

#### # `defnet`
`defnet` defines a new network. A network is a structure that contains a number of routers $\geq 0$. Every router within a network must have unique addresses. Routers belonging to differing networks may have identical addresses, but must have unique subnet masks.

#### # `delnet`
`delnet` deletes an existing network. `delnet` implicitly calls `delrtr` for all routers within the network.

#### # `modnet`
`modnet` modifies an existing network. `modnet` is used to re-set any flags belonging to `defnet`.

#### # `rtnet`
`rtnet` defines a new route between two existing routers belonging to differing networks.

#### # `defrtr`
`defrtr` defines a new router.

#### # `delrtr`
`delrtr` deletes a router. `delrtr` implicitly calls `delrt` for all routes to and from the router.

#### # `modrtr`
`modrtr` modifies an existing router. `modrtr` is used to re-set any flags belonging to `defrtr`

#### # `rtrtr`
`rtrtr` defines a new route between two existing routers belonging to the same network.

#### # `delrt`
`delrt` deletes an existing route.

#### # `modrt`
`modrt` modifies an existing route. `modrt` is used to re-set any flags belonging to `rtrtr` or `rtnet`.

### Evaluation Tools
Users will be able to evaluate existing networks using a set of provided shell commands. These commands can be used to evaluate networks based upon various criteria (throughput, energy conservation, etc.). 

#### # `setalgo`
`setalgo` defines the pathfinding algorithm called by `eval`. `setalgo` defines the body of the internal function `algo`. Any algorithm passed to `setalgo` must pass an internal test before it is accepted. If the algorithm passed to `setalgo` does not pass the internal test, it will be rejected. `eval` and `evalwith` will not be accepted as valid shell commands without a valid pathfinding algorithm. 

#### # `setto`
`setto` defines the *to* router. `eval` and `evalwith` will not be accepted as valid shell commands without a valid *to* router.

#### # `setfrom`
`setto` defines the *from* router. `eval` and `evalwith` will not be accepted as valid shell commands without a valid *from* router.

#### # `eval`
`eval` returns a pathfinding evaluation on the current network. `eval` requires a valid pathfinding algorithm, *to* router, and *from* router to be internally set before it considered a valid shell command.

#### # `evalwith`
`evalwith` implicitly calls `setalgo`, `setto`, `setfrom`, and `eval`. `setalgo`, `setto`, and `setfrom` must be internally accepted as valid shell commands before `eval` is called.

### A Note
Features may be removed or added depending upon available development time and reconsidered scopes. Information provided in this document may not accurately reflect the state of the current software version. It is recommended that users refer to the version-specific documentation or the provided `README.md`.