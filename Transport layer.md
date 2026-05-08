---
tags:
  - CPE400
---
The transport layer is layer $4$ of the [[Open systems interconnection (OSI) model]].

The transport layer is a conceptual division of methods in the layered architecture of protocols in the network stack of the Internet protocol suite and the OSI model.

At the transport layer there are two protocols in use: [[Transmission control protocol (TCP)]] and [[User datagram protocol (UDP)]].

The transport layer accept messages from the [[Application layer]] as application data. It does not care if this data is part of the setup process, actual data to be transferred, or some other control message. It just sees the data as a block of data to be transported to the receiving end's transport layer.

Application data is often very large and must be split into chunks (segments) so that it can be transported by the [[Network layer]]. This segmentation is carried out at the transport layer; the size of the segments is set by the maximum segment size (MSS). TCP segments are often referred to as TCP packets. Each segment has a header and payload.

## TCP Tahoe & Reno
While both consider retransmission timeout (RTO) and duplicate ACKs as packet loss events, the behaviour of Tahoe and 