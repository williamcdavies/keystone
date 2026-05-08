---
tags:
  - CPE400
aliases:
  - Autonomous system (AS)
---
An autonomous system (AS) is a collection of connected [[Internet protocol (IP)]] routing prefixes under the control of one or more network operators on behalf of a single administrative entity or domain, that presents a common and clearly defined routing policy to the Internet. Each AS is assigned an autonomous system number (ASN), for use in [[Border gateway protocol (BGP)]] routing.

## ASN Table
A complete table of available 16-bit ASN:

| Number        | Description                                       | Reference          |
|:------------- |:------------------------------------------------- |:------------------ |
| 0             | Reserved for RPKI unallocated space invalidation  | RFC 6484, RFC 7607 |
| 1 - 23455     | Public ASNs                                       |                    |
| 23456         | Reserved for AS Pool Transition                   | RFC 6793           |
| 23457 - 64495 | Public ASNs                                       |                    |
| 64496 - 64511 | Reserved for use in documentation and sample code | RFC 5398           |
| 64512 - 65534 | Reserved for private use                          | RFC 1930, RFC 6996 |
| 65535         | Reserved                                          | RFC 7300           |
