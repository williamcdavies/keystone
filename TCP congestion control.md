---
tags:
  - CPE400
---
[[Transmission control protocol (TCP)]] uses a congestion control algorithm that includes various aspects of additive increase/multiplicative decrease (AIMD) scheme, along with other schemes including slow start (SS) and a congestion window (CWND).

## TCP Tahoe
When a loss occurs, retransmit is sent, half of the current CWND is saved as `ssthresh` and slow start begins again from `initcwnd`.

## TCP Reno
A fast retransmit is sent, half of the current CWND is saved as `ssthresh` and as new CWND, thus skipping slow start and going directly to the congestion avoidance algorithm. The overall algorithm here is called fast recovery.

Fast retransmit only occurs following loss signalled by $3$ duplicate acknowledgements. Otherwise, TCP Tahoe is used.