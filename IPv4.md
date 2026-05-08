---
tags:
  - CPE400
---
## IPv4 Packet Structure

|                          |               |                          |                           |            |            |                           |
|:------------------------ |:------------- |:------------------------ |:------------------------- | ---------- |:---------- |:------------------------- |
| Version (4 bits)         | HLEN (4 bits) | Type of Service (8 bits) | Total Length (16 bits)    | ...        | ...        | ...                       |
| Identification (16 bits) | ...           | ...                      | Res       (1 bit)         | DF (1 bit) | MF (1 bit) | Fragment Offset (13 bits) |
| Time to Live (8 bits)    | ...           | Protocol (8 bits)        | Header Checksum (16 bits) | ...        | ...        | ...                       |
| Source IP (32 bits)      | ...           | ...                      | ...                       | ...        | ...        | ...                       |
| Destination IP (32 bits) | ...           | ...                      | ...                       | ...        | ...        | ...                       |
| Options (0 to 40 bytes)  | ...           | ...                      | ...                       | ...        | ...        | ...                       |
| DATA (20 to 65546 bytes) | ...           | ...                      | ...                       | ...        | ...        | ...                       |