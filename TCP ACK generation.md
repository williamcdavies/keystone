---
tags:
  - CPE400
---

| Event @ Receiver                                                                                                         | Receiver Action                                                                                 |
|:------------------------------------------------------------------------------------------------------------------------ |:----------------------------------------------------------------------------------------------- |
| Arrival of in-order segment with expected sequence number. All data up to expected sequence number already acknowledged. | Delayed ACK. Wait up to 500ms for next segment. If no segment, send ACK.                        |
| Arrival of in-order segment with expected sequence number. One other segment has ACK pending.                            | Wait for the timer to complete 500ms. Send cumulative ACK, acknowledging all in-order segments. |
| Arrival of out-of-order segment with higher than  expected sequence number. One other segment has ACK pending.           | Immediately send duplicate ACK, indicating sequence number of next expected byte.               |
| Arrival of segment that partially or completely fills gap.                                                               | Immediately send ACK, provided that segment starts at lower end of gap.                         |
