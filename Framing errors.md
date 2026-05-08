---
tags:
  - CPE301
---
In serial communications, a framing error is the result of reading a data frame - a string of symbols which are grouped in blocks - at the wrong starting point. A framing error in an asynchronous stream usually recovers quickly, but a framing error in a synchronous stream produces gibberish at the end of the packet. Framing errors can be detected with parity bits.