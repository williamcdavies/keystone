---
tags:
  - CPE400
---
DHCP is a network management protocol used on [[Internet protocol (IP)]] networks for automatically assigning IP addresses and other communication parameters to devices connected to the network using a client-server architecture.

## Operation
The DHCP employs a connectionless service model, using the [[User datagram protocol (UDP)]]. It is implemented with two UDP port numbers for its operations which are the same as for the bootstrap protocol. The server listens on UDP port number $67$, and the client listens on UPD port number $68$.

DHCP operations fall into four phases: server discovery, IP lease offer, IP lease request, and IP lease acknowledgement. These stages are often abbreviated as DORA for discovery, offer, request, and acknowledgement.

### Discovery
The DHCP client broadcasts a DHCPDISCOVER message on the network subnet using the destination address `255.255.255.255`.

### Offer
When a DHCP server receives a DHCPDISCOVER message from a client, which is an IP address lease request, the DHCP server reserves an IP address for the client and makes a lease offer by sending a DHCPOFFER message to the client. This message may contain the client's Client ID, the IP address that the server is offering, the subnet mask, the lease duration, and the IP address of the DHCP server making the offer.

### Request
In response to the DHCP offer, the client replies with a DHCPREQUEST message, broadcast to the server, requesting the offered address. A client can receive DHCP offers from multiple servers, but it will accept only one DHCP offer.

The client must send the server identification option in the DHCPREQUEST message, indicating the server whose offer the client has selected. When other DHCP servers receive this message, they withdraw any offers that they have made to the client and return their offered IP address to the pool of available addresses.

### Acknowledgement
When the DHCP server receives the DHCPREQUEST message from the client, the configuration process enters its final phase. The acknowledgement phase involves sending a DHCPACK packet to the client. This packet includes the lease duration and any other configuration information that the client might have requested. At this point, the IP configuration process is completed.