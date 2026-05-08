---
tags:
  - CPE400
---
Reverse-path forwarding (RPF) is a technique used in modern [[Routers]] for the purposes of ensuring loop-free forwarding of multicast packets in [[Multicast routing]] and to help prevent [[Internet protocol (IP)]] address spoofing in unicast routing.

## Multicast RPF
When a multicast packet enters a router's interface, the router looks up the list of networks that are reachable via that interface (i.e., it checks the paths by which the packet could have arrived). If the router finds a matching routing entry for the source IP address of the multicast packet, the RPF check passes and the packet is forwarded to all other interfaces that are participating in that multicast group. If the RPF check fails, the packet is dropped.