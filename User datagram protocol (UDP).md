---
tags:
  - CPE400
---
UDP is one of the core communication protocols of the Internet Protocol suite used to send messages to other hosts on an IP network.

UDP is a connectionless protocol, meaning that messages are sent without negotiating a connection and that UDP does not keep track of what it has sent. 

## UDP segment structure
|                        |     |     |     |     |     |     |     |                             |
|:---------------------- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--------------------------- |
| Source Address 16 bits | ... | ... | ... | ... | ... | ... | ... | Destination Address 16 bits |
| Length 16 bits         | ... | ... | ... | ... | ... | ... | ... | Checksum 16 bits            |
| Data X bits            | ... | ... | ... | ... | ... | ... | ... | ...                         |