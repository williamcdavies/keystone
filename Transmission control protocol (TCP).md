---
tags:
  - CPE400
---
TCP is one of the main protocols of the Internet Protocol suite. TCP provides reliable, ordered, and error-checked delivery of a stream of bytes between applications running on hosts communicating via an IP network.

TCP is connection-oriented, meaning that the sender and receiver need to establish connection based on agreed parameters. They do this through a three-way handshake procedure.

## TCP segment structure
|                                    |                 |     |     |     |     |     |     |                                  |
|:---------------------------------- |:--------------- |:--- |:--- |:--- |:--- |:--- |:--- |:-------------------------------- |
| Source Port Address 16 bits        | ...             | ... | ... | ... | ... | ... | ... | Destination Port Address 16 bits |
| Sequence Number 32 bits            | ...             | ... | ... | ... | ... | ... | ... | ...                              |
| Acknowledgement Number 32 bits     | ...             | ... | ... | ... | ... | ... | ... | ...                              |
| HLEN 4 bits                        | Reserved 6 bits | URG | ACK | PSH | RST | SYN | FIN | Window Size 16 bits              |
| Checksum 16 bits                   | ...             | ... | ... | ... | ... | ... | ... | Urgent Pointer 16 bits           |
| Options and Padding Up to 40 bytes | ...             | ... | ... | ... | ... | ... | ... | ...                              |

### SYN
The SYN flag, short for "synchronise," is the first signal sent when a client wants to establish a TCP connection with a server. It initiates the process known as the TCP three-way handshake. This flag indicates that the client is ready to begin communication and wants to establish a session. The SYN segment includes an initial sequence number (ISN) that begins the process of tracking data packets exchanged between the two parties.

### ACK
The ACK flag, or acknowledgment flag, is used to confirm the receipt of data or control information. This flag is used in nearly all TCP segments following the initial SYN. Every time a host receives a data packet, it sends back an ACK with an acknowledgement number that indicates the next expected byte. This forms the backbone of TCP's reliability mechanism, ensuring that no data is lost or disordered during transmission.

### FIN
The FIN flag is used to terminate a TCP session gracefully. When a host no longer has data to send, it sets the FIN flag in a segment and sends it to the other side. This signals that the sender has finished transmitting, although the session isn't closed until the other side responds with an acknowledgment and possibly sends it owns FIN.

### RST
The RST flag, or reset flag, is used to abruptly terminate a TCP session. Unlike the FIN flag, which is part of a planned and mutual termination, the RST flag indicates that something has gone wrong and the connection should be shut down immediately. It can be triggered by various situations, such as an attempt to connect to a closed port, receipt or corrupt or unexpected data, or the discovery of a protocol error.

### PSH
The PSH flag, or push function, tells the receiving system to immediately pass the data to the application rather than buffering it. This is especially important in applications that require real-time communication, such as instant messaging or online gaming. When the PSH flag is set, it ensures that the data reaches the application layer as soon as it arrives.

### URG
The URG flag, or urgent flag, indicates that a segment contains urgent data that should be prioritised. It is sued in conjunction with the Urgent Pointer field in the TCP header, which specifies the end of the urgent data within the segment. Historically, the URG flag was used in legacy systems such as Telnet to interrupt or control sessions.