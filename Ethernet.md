---
tags:
  - CPE400
---
Ethernet is a family of wired computer networking technologies commonly used in local area networks, metropolitan area networks, and wide area networks. It was first standardised as [[IEEE 802.3]].


| 7 bytes (`10101010`) 1 byte (`10101011`) | 6 bytes                   | 6 bytes              | 2 bytes | 42 - 1500 bytes | 4 bytes                     |
|:---------------------------------------- |:------------------------- |:-------------------- |:------- |:--------------- |:--------------------------- |
| preamble                                 | destination address (MAC) | source address (MAC) | type    | payload         | [[Cyclic redundancy check]] |


| Year | Speed    | Common name                                          | IEE#     | Dist               | Media                                                          |
|:---- |:-------- |:---------------------------------------------------- |:-------- |:------------------ |:-------------------------------------------------------------- |
| 1973 | 3 Mb/s   | Xerox Ethernet                                       | -        | ?                  | Coax                                                           |
| 1976 | 10 Mb/s  | Ethernet 1                                           | -        | 500m               | RG-11 coax                                                     |
| 1989 | 10 Mb/s  | 10BASE-T                                             | 802.3    | 100m               | Cat 3 UTP copper                                               |
| 1994 | 100 Mb/s | 100BASE-TX                                           | 802.3u   | 100m               | Cat 5 UTP copper                                               |
| 1999 | 1 Gb/s   | 1000BASE-T ("gigabit")                               | 802.3ab  | 100m               | Cat 5e, 6 UTP copper                                           |
| 2006 | 10 Gb/s  | 10GBASE-T ("10 gig")                                 | 802.3an  | 100m               | Cat 6a, 7, 7a UTP                                              |
| 2009 | 40 GB/s  | 40GBASE-CR4/40GBASE-SR4                              | P802.3ba | 10m/100m           | UTP copper/MM fibre                                            |
| 2009 | 100 GB/s | 100GBASE-CR10/100GBASE-SR10                          | P802.3ba | 10m/100m           | UTP copper/MM fibre                                            |
| 2018 | 200 GB/s | 200GBASE-FR4/200GBASE-LR4                            | 802.3bs  | 2km/10km           | CWDM fiber/CWDM fiber                                          |
| 2018 | 400 Gb/s | 400GBASE-SR16/400GBASE-DR4/400GBASE-FR8/400GBASE-LR8 | 802.3bs  | 100m/500m/2km/10km | MM fiber (16 strand)/MM fiver (4 strand)/CWDM fiber/CWDM fiber |
| 2020 | 1 Tb/s   | TbE                                                  | TBD      | TBD                | TBD                                                            | 


| Parameter         | Units | Cat 5b/Class D | Cat 5e | Cat 6/Class E | Cat 6a/Class EA | Cat 7/Class F | Cat 7a/Class FA | Cat 8/Class I |
|:----------------- |:----- |:-------------- |:------ |:------------- |:--------------- |:------------- |:--------------- |:------------- |
| Frequency range   | MHz   | 100            | 100    | 250           | 500             | 600           | 1000            | 2000          |
| Attenuation       | dB    | 24             | 24     | 21.7          | 18.4            | 20.8          | 60              | 50            |
| NEXT              | dB    | 27.1           | 30.1   | 39.9          | 59              | 62.1          | 60.4            | 36.5          |
| ELFEXT            | dB    | 17             | 17.4   | 23.2          | 43.1            | 46.0          | 35.1            | -             |
| Return loss       | dB    | 8              | 10     | 12            | 32              | 14.1          | 61.93           | 8             |
| Propagation delay | ns    | 548            | 548    | 548           | 548             | 504           | 534             | 548           | 
