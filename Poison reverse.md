---
tags:
  - CPE400
---
Poison Reverse is often used within [[Distance-vector routing protocols]] to solve the [[Count-to-infinity problem]]. Practically, poison reverse can be thought of as an alternative to split horizon. With poison reverse, route advertisements that would be suppressed by split horizon are instead advertised with a distance of infinity.

The basic idea of poison reverse is to make sure that a path does not turn back into the same node if a cost has changed within the network. An example of this would be: Node $Z$ routes via node $Y$ to destination $X$. If the cost between $Y$ and $X$ increases, the count to infinity problem will occur. To avoid it, we implement poison reverse. As long as $Z$ routes via node $Y$ to get to $X$, $Z$ will tell a white lie to $Y$: $Z$ will announce to $Y$ an infinite cost to the destination $X$.