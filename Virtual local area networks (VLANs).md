---
tags:
  - CPE400
---
A virtual local area network (VLAN) is a [[Local area networks (LANs)|Local area network (LAN)]] broadcast domain that is partitioned and isolated in a virtual network at the [[Data link layer]]. A VLAN behaves like a virtual [[Network switches|Network switch]] or network link that can share the same physical structure with other VLANs while staying logically separate from them.

VLANs work by applying tags to network [[Frames]] that are forwarded within the broadcast domain, creating the appearance and functionality of network traffic that behaves as if it were split between separate networks.

Switches supporting VLAN capabilities can be configured to define multiple virtual LANS over a single physical LAN infrastructure.

A trunk port carries frames between VLANs defined over multiple physical switches.

## 802.1Q VLAN Frame Format

| 7 bytes (`10101010`) 1 byte (`10101011`) | 6 bytes                   | 6 bytes              | 2 bytes                 | 2 bytes                 | 2 bytes | 42 - 1500 bytes | 4 bytes                                |
|:---------------------------------------- |:------------------------- |:-------------------- |:----------------------- |:----------------------- |:------- |:--------------- |:-------------------------------------- |
| preamble                                 | destination address (MAC) | source address (MAC) | Tag Protocol Identifier | Tag Control Information | type    | payload         | Recomputed [[Cyclic redundancy check]] |
