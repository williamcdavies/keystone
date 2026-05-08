---
tags:
  - CPE400
---
The Internet Group Management Protocol (IGMP) is a communications protocol used by hosts and adjacent [[Routers]] on [[IPv4]] networks to establish multicast group memberships. IGMP is an integral part of [[IP multicasting]] and allows the network to direct multicast transmissions only to hosts that have requested them.

## Messages 
There are several types of IGMP messages:

### Queries

#### General Membership Queries
Sent by multicast routers to determine which multicast addresses are of interest to systems attached to the network(s) they serve to refresh the group membership state for all systems on its network.

#### Group-specific Membership Queries
Used for determining the reception state for a particular multicast address.

#### Group-and-source-specific queries
Allow the router to determine if any systems desire reception of messages sent to a multicast group from a source address specified in a list of unicast addresses.

### Membership Reports
Sent by multicast receivers in response to a membership query or asynchronously when first registering for a multicast group.

### Leave Reports
Sent by multicast receivers when specified multicast transmissions are no longer needed at the receiver.

## IGMPv2 Packet Structure

| 0             | 1                     | 2        | 3      |
|:------------- |:--------------------- | -------- |:------ |
| Type          | Maximum Response Time | Checksum | -      |
| Group Address | -                     | -        | -      |
| 8 bits        | 8 bits                | 8 bits   | 8 bits |

## Type: 8 Bits
Indicates the message type as follows:

| Message           | Type Value |
|:----------------- |:---------- |
| Query             | 0x11       |
| Membership Report | 0x16       |
| Leave Report      | 0x17       |

## Example

```
Consider the following network:

A - B - C - R (Router)

A:
| Group        | Timer |
|:------------ |:----- |
| `255.14.0.0` | 30    |
| `228.42.0.0` | 12    |
| `230.43.0.0` | 80    |

B:
| Group        | Timer |
|:------------ |:----- |
| `255.42.0.0` | 48    |
| `238.71.0.0` | 50    |

C:
| Group        | Timer |
|:------------ |:----- |
| `255.14.0.0` | 62    |
| `238.43.0.0` | 70    |

A query message was received at time 0; the random delay time  
for each group is shown next to the group address. Show the  
sequence of report messages.
```

> [!example]
Time 12: The timer for `228.42.0.0` in host $A$ expires and a membership report is sent, which is received by the router and every host including host $B$ which cancels its timer for `228.42.0.0`.
>
Time 30: The timer for `225.14.0.0` in host $A$ expires and a membership report is sent, which is received by the router and every host including host $C$ which cancels its timer for `225.14.0.0`.
>
Time 50: The timer for `238.71.0.0` in host $B$ expires and a membership report is sent, which is received by the router and every host.
>
Time 70: The timer for `230.43.0.0` in host $C$ expires and a membership report is sent, which is received by the router and every host including host $A$ which cancels its timer for `230.43.0.0`.