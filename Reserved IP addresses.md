---
tags:
  - CPE400
---

| Address block ([[Classless inter-domain routing (CIDR)]]) | Address range                    | Number of addresses | Scope           | Description                                                  |
|:--------------------------------------------------------- |:-------------------------------- |:------------------- |:--------------- |:------------------------------------------------------------ |
| `0.0.0.0/8`                                               | `0.0.0.0` - `0.255.255.255`      | $16777216$          | Software        | Current network                                              |
| `10.0.0.0/8`                                              | `10.0.0.0` - `10.255.255.255`    | $16777216$          | Private network | Used for local communications within a private network       |
| `127.0.0.0/8`                                             | `127.0.0.0`  - `127.255.255.255` | $16777216$          | Host            | Used for loopback addresses to the local host                |
| `240.0.0.0/4`                                             | `240.0.0.0` - `255.255.255.254`  | $268435455$         | Internet        | Reserved for future use                                      |
| `255.255.255.255/32`                                      | `255.255.255.255`                | $1$                 | Subnet          | Reserved for the "limited [[Broadcast]] destination address" |

