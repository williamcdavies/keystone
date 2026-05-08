---
tags:
  - CPE400
---
The Routing Information Protocol (RIP) is one of the oldest [[Distance-vector routing protocols]] which employs the hop count as a routing metric. RIP prevents routing loops by implementing a limit on the number of hops allowed in a path from source to destination. The largest number of hops allowed for RIP is $15$, which limits the size of networks that RIP can support.

When starting up, and every $30$ seconds thereafter, a router with RIPv1 implementation broadcasts to `255.255.255.255` a request message through every RIPv1 enabled interface. Neighbouring routers receiving the request message respond with a RIPv1 segment, containing their routing table.