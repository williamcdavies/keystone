---
tags:
  - CPE400
---
When packets arrive at a router, they must be serviced. Since routers can only service one packet at a time, packets that arrive when the router is busy are placed in a queue/buffer. Queueing delay is the amount of time it takes for a packet to be serviced following its arrival.

The average queueing delay for any given packet is given by $\frac{1}{ \mu - \lambda }$ where $\mu$ is the number of packets per second the router can service and $\lambda$ is the average rate at which packets are arriving to be serviced