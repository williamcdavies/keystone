---
tags:
  - CPE400
---
A network bridge is a computer networking device that creates a single, aggregate network from multiple communication networks or network segments. This function is called network bridging. Bridging is a distinct from routing. Routing allows multiple networks to communicate independently and yet remain separate, whereas bridging connects two separate networks as if they were a single network. In the [[Open systems interconnection (OSI) model]], bridging is performed in the [[Data link layer]]. If one or more segments of the bridged network are wireless, the device is known as a wireless bridge.

## Forwarded
The frame is sent only onto the LAN segment where the destination is located. The bridge examines the source MAC address fields to find specific device locations.

## Filtered
The frame is dropped by the bridge. No message is sent back to the source

## Flooded
The frame is sent to every LAN segment attached to the bridge. This is done for broadcast and multicast traffic.