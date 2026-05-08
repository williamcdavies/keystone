---
tags:
  - CS219
---
Temporal locality is a type of [[Locality of reference|Reference locality]]. If at one point a particular memory location is referenced, then it is likely that the same location will be referenced again in the near future. There is temporal proximity between adjacent references to the same memory location. In this case it is common to make efforts to store a copy of the referenced data in faster memory storage, to reduce the latency of subsequent references. Temporal locality is a special case of [[Spatial locality]], namely when the prospective location is identical to the present location.