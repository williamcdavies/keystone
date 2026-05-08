---
tags:
  - CPE400
aliases:
  - Medium access control (MAC) address
---
A MAC address (medium access control address) is a unique identifier assigned to a [[Network interface controllers (NIC)|Network interface controller (NIC)]] for use as a network address in communications within a network segment.

MAC addresses are primarily assigned by device manufacturers, and therefore often referred to as the burned-in address, or as an [[Ethernet]] hardware address, hardware address, or physical address.


| 1st octet                          | 2nd octet                          | 3rd octet                          | 4th octet    | 5th octet    | 6th octet    |
|:---------------------------------- |:---------------------------------- |:---------------------------------- |:------------ |:------------ |:------------ |
| Organisationally Unique Identifier | Organisationally Unique Identifier | Organisationally Unique Identifier | NIC specific | NIC specific | NIC specific |


| 1st octet |     |     |     |     |     |                                             |                          |
|:--------- |:--- |:--- |:--- |:--- |:--- |:------------------------------------------- |:------------------------ |
| b7        | b6  | b5  | b4  | b3  | b2  | b1                                          | b0                       |
|           |     |     |     |     |     | 0: globally unique, 1: locally administered | 0: unicast, 1: multicast |
