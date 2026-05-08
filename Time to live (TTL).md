---
tags:
  - CPE400
---
## IP Packets
Under the [[Internet protocol (IP)]], TTL is an 8-bit field. In the [[IPv4]] header, TTL is the 9th octet of 20. In the [[IPv6]] header, it is the 8th octet of 40. The maximum TTL value is 255, the maximum value of a single octet. A recommended initial value is 64 ($0=$ host, $64=$ within-region, $128=$ within-continent, $255=$ unrestricted).