---
tags:
  - CPE400
---
Selective Repeat is part of the automatic repeat request (ARQ). With selective repeat, the sender sends a number of frames specified by a window size even without the need to wait for individual ACK from the receiver as in [[Go-back-n ARQ]]. The receiver may selectively reject a single frame, which may be retransmitted alone; this contrasts with other forms of ARQ, which must send every frame from that point again. The receiver accepts out-of-order frames and buffers them. The send individually retransmits frames that have timed out.