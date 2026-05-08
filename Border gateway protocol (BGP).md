---
tags:
  - CPE400
---
Border Gateway Protocol (BGP) is a standardised [[Exterior gateway protocols (EGPs)|Exterior gateway protocol (EGP)]] designed to exchange routing and reachability information among [[Autonomous systems (ASs)]] on the Internet. BGP is classified as a path-vector routing protocol, and it makes routing decisions based on paths, network policies, or rule-sets configured by a network administrator.

## Packet Format

### Message Header Format

| bit offset | 0 - 15                                                           | 16 - 23 | 24 - 31 |
|:---------- |:---------------------------------------------------------------- |:------- |:------- |
| 0          | Marker (awlays: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff) | -       | -       |
| 32         | "                                                                | -       | -       |
| 64         | "                                                                | -       | -       |
| 96         | "                                                                | -       | -       |
| 128        | Length                                                           | Type    | -       |

- Marker: Included for compatibility, must be set to all ones.
- Length: Total length of the message in octets, including the header
- Type: Type of BHP message. The following values are defined:
	- OPEN (1)
	- UPDATE (2)
	- NOTIFICATION (3)
	- KEEPALIVE (4)
	- ROUTE-REFRESH (5)

### OPEN Packet
Version (8 bits)
- Version of BGP used.
My AS (16 bits)
- Senders autonomous system number.
Hold Time (16 bits)
- Timeout timer, used to calculate KeepAlive messages. Default 90 seconds.
BGP Identifier (32 bits)
- IP-address of sender.
- Optional Parameters Length (8 bits): total length of the Optional parameters field.

#### Example of OPEN Message

```
Type: Open Message (1)
Version: 4
My AS: 64496
Hold Time: 90
BGP Identifier: _192.0.2.254_
Optional Parameters Length: 16
Optional Parameters:
 Capability: Multiprotocol extensions capability (1)
 Capability: Route refresh capability (2)
 Capability: Route refresh capability (Cisco) (128)
```

### UPDATE Packet
Only changes are sent, after initial exchange, only difference (add/change/removed) are sent.

#### Example of UPDATE Message

```
Type: UPDATE Message (2)
Withdrawn Routes Length: 0
Total Path Attribute Length: 25
Path attributes
 ORIGIN: IGP
 AS_PATH: 64500
 NEXT_HOP: 192.0.2.254
 MULTI_EXIT_DISC: 0
Network Layer Reachability Information (NLRI)
 _192.0.2.0/27_
 _192.0.2.32/27_
 _192.0.2.64/27_
```

### NOTIFICATION Packet
If there is an error it is because one of the fields in the OPEN or UPDATE message does not match between the peers, e.g., BGP version mismatch, the peering router expects a different My AS, etc. The router then sends a Notification message to the peer indicating why the error occurred.

#### Example of NOTIFICATION Message

```
Type: NOTIFICATION Message (3)
Major error Code: OPEN Message Error (2)
Minor error Code (Open Message): Bad Peer AS (2)
Bad Peer AS: 65200
```

### KEEPALIVE Packet
KeepAlive messages are sent periodically, to verify that remote peer is still alive. keepalives should be sent at intervals of one third the `holdtime`.

#### Example of KEEPALIVE Message

```
Type: KEEPALIVE Message (4)
```

### ROUTE-REFRESH
Allows for soft updating of `Adj-RIB-in`, without resetting connection.

#### Example of ROUTE-REFRESH Message

```
Type: ROUTE-REFRESH Message (5)
Address family identifier (AFI): IPv4 (1)
Subtype: Normal route refresh request [RFC2918] with/without ORF [RFC5291] (0)
Subsequent address family identifier (SAFI): [Unicast](https://en.wikipedia.org/wiki/Unicast "Unicast") (1)
```