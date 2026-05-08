---
tags:
  - CPE400
---
Carrier-sense multiple access with collision detection (CSMA/CD) is a medium access control (MAC) method used most notably in early [[Ethernet]] technology for [[Local area networks (LANs)|Local area networking (LAN)]]. It uses carrier-sensing to defer transmission until no other stations are transmitting. This is used in combination with collision detection in which a transmitting station detects collisions by sensing transmissions form other stations while it is transmitting a [[Frames|Frame]]. When this collision condition is detected, the station stops transmitting that frame, transmits a jam signal, and then waits for a random time interval before trying to resend the frame.

CSMA/CD is a modification of pure [[Carrier-sense multiple access (CSMA)]]. CSMA/CD is used to improve CSMA performance by terminating transmission as soon as a collision is detected, thus shortening the time required before a retry can be attempted.