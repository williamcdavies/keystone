---
tags:
  - CPE400
---
The [[Domain name system (DNS)]] specified a database of information elements for network resources. The types of information elements are categorised and organised with a list of DNS record types, the resource records (RRs).

## Resource Record Fields

| Field    | Description                                                                                       |                    Length |
|:-------- |:------------------------------------------------------------------------------------------------- | -------------------------:|
| NAME     | Name of the node to which this record pertains                                                    |                  Variable |
| TYPE     | Type of RR in numeric form (e.g., 15 for MX RRs)                                                  |                       $2$ |
| CLASS    | Class code                                                                                        |                       $2$ |
| TTL      | Count of seconds that the RR stays valid (The maximum is $2^{31} - 1$, which is about $68$ years) |                       $4$ |
| RDLENGTH | Length of RDATA field (specified in octets)                                                       |                       $2$ |
| RDATA    | Additional RR-specific data                                                                       | Variable, as per RDLENGTH |

## Resource Records


| Type  | Type id (decimal) | Defining RFC   | Description           | Function                                                         |
|:----- |:----------------- |:-------------- |:--------------------- |:---------------------------------------------------------------- |
| A     | 1                 | RFC 1035       | Address record        | Returns a $32$-bit IPv4 address                                  |
| NS    | 2                 | RFC 1035       | Name server record    | Delegates a DNS zone to use the given authoritative name servers |
| CNAME | 5                 | RFC 1035       | Canonical name record | Alias of one name to another                                     |
| MX    | 15                | RFC 1035, 7505 | Mail exchange record  | List of mail exchange servers that accept email for a domain     |
