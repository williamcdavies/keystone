---
tags:
  - CPE400
---
## IPv6 Packet Structure

|                                |                   |                      |                      |                    |
|:------------------------------ |:----------------- |:-------------------- |:-------------------- |:------------------ |
| Version (4 bits)               | Priority (8 bits) | Flow Label (20 bits) | ...                  | ...                |
| Payload Length (16 bits)       | ...               | ...                  | Next Header (8 bits) | Hop Limit (8 bits) |
| Source Address (128 bits)      | ...               | ...                  | ...                  | ...                |
| Destination Address (128 bits) | ...               | ...                  | ...                  | ...                |
