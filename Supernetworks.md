---
tags:
  - CPE400
---
A supernetwork is an [[Internet protocol (IP)]] that is formed by aggregation of multiple networks (or subnets) into a larger network. The new routing prefix for the aggregate network represents the constituent networks in a single routing table entry/ The process of forming a supernet is called supernetting, prefix aggregation. route aggregation, route summarisation.

```
Form a supernet by aggregating the following address set:

192.168.98.0
192.168.99.0
192.168.100.0
192.168.101.0
192.168.102.0
192.168.105.0
```

> [!example]
> 1. Convert each address to binary:
>
| Address         | First Octet | Second Octet | Third Octet | Fourth Octet |
|:--------------- |:----------- |:------------ |:----------- |:------------ |
| `192.168.98.0`  | 11000000    | 10101000     | 01100010    | 00000000     |
| `192.168.99.0`  | 11000000    | 10101000     | 01100011    | 00000000     |
| `192.168.100.0` | 11000000    | 10101000     | 01100100    | 00000000     |
| `192.168.101.0` | 11000000    | 10101000     | 01100101    | 00000000     |
| `192.168.102.0` | 11000000    | 10101000     | 01100110    | 00000000     |
| `192.168.105.0` | 11000000    | 10101000     | 01101001    | 00000000     |
>
> 2. Determine the largest contiguous pattern of shared bits across address set. In the case above, the largest contiguous pattern of shared bits is 11000000 10101000 0110. The summary route is found by setting the remaining bits to zero. It is followed by a slash and then a number of common bits:
>
| Address        | Netmask | First Octet | Second Octet | Third Octet | Fourth Octet |
|:-------------- |:------- |:----------- |:------------ |:----------- |:------------ |
| `192.168.96.0` | /20     | 11000000    | 10101000     | 01100000    | 00000000     |
>
The summarised route is `192.168.96.0/20`. The subnet mask is `255.255.240.0`. This summarised route also contains networks that were not in the address set, namely, `192.168.96.0`, `192.168.97.0`, `192.168.103.0`, `192.168.104.0`, `192.168.106.0`, `192.168.107.0`, `192.168.108.0`, `192.168.109.0`, `192.168.110.0`, and `192.168.111.0`. It must be assured that the missing networks do not exist outside of this route.