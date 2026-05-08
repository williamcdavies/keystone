---
tags:
  - CPE400
---
Transmission delay is the amount of time required to push all the packet's bits into the wire. In other words, this is the delay caused by the data-rate of the link.

Transmission delay is a function of the packet's length and has nothing to do with the distance between the two nodes. This delay is proportional to the packet's length in bits. It is given by the following formula:
$$D_T = \frac{N}{R}$$

where:
- $D_T$ is the transmission delay in seconds;
- $N$ is the number of bits
- $R$ is the rate of transmission