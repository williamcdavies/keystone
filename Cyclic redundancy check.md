---
tags:
  - CPE201
---
A cyclic redundancy check is an error-detecting method used in digital networks and storage devices to detect accidental changes to digital data. Blocks of data entering these systems are appended with a short check value based on the remainder of a polynomial division of their contents. On retrieval, the calculation is repeated and, in the event the check values do not match, [[Corrective action can be taken against data corruption]].

The CRC process is as follows:
1. Select a fixed generator polynomial; this code is understood in advance by both the sending and receiving devices and must be the same for both.
2. Append a $(k - 1)$ $0$s to the data block where $k$ represents the number of bits in the generator code obtained from the generator polynomial
3. Use $\bmod$ to divide the data block by the generator code and store remainder $R$
4. At the receiving end, the receiver divides the incoming data block by the same generator code as used by the sender.
5. If $R = 0$, there is no error detected (it is possible in rare cases for multiple errors to cancel). If $R \neq 0$, an error has been detected in the transmission and a retransmission is requested by the receiver.