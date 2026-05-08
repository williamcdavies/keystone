---
tags:
  - CPE400
---
The data link layer is layer $2$ of the [[Open systems interconnection (OSI) model]].

The data link provides for the transfer of data frames between hosts connected to the physical link. Within the semantics of the OSI model, the protocols of the data link protocols respond to service requests from the [[Network layer]], and perform their function by issuing service requests to the [[Physical layer]]. That transfer can be reliable or unreliable; many data link do not have acknowledgments of successful frame reception and acceptance, and some data link protocols might not even perform any check for transmission errors. In those cases, higher-level protocols must provide flow control, error checking, acknowledgements, and retransmission.
