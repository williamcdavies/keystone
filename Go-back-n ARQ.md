---
tags:
  - CPE400
---
Go-Back-N ARQ is a specific instance of the automatic repeat request protocol in which the sending process continues to send a number of frames specified by a windows size even without receiving an ACK packet from the receiver. It is a special case of the general sliding window protocol with the transmit window size of $N$ and receive window size of $1$. It can transmit $N$ frames to the peer before requiring an ACK.

The receiver process keeps track of the sequence number of the next frame it expects to receive. It will discard any frame that does not have the exact sequence number it expects and will send an ACK for the last correct in-order frame. Once the sender has sent all the of the frames in its window, it will detect that all of the frames since the first lost frame are outstanding, and will go back to the sequence number of the last ACK it received from the receiver process and fill its window starting with that frame and continue the process over again.