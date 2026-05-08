---
tags:
  - CPE400
---
[[Transmission control protocol (TCP)]] uses a sliding window for flow control.

The TCP sliding window determines the number of unacknowledged bytes, $x$, that one system can send to another. Two factors determine the value of $x$:
- The size of the send buffer on the sending system
- The size and available space in the receive buffer on the receiving system

The sending system cannot send more bytes than space is available in the receive buffer on the receiving system. TCP on the sending system must wait to send more data until all bytes in the current send buffer are acknowledged by TCP on the receiving system.

On the receiving system, TCP stores received data in a receive buffer. TCP acknowledges receipt of the data, and advertises a new receive window to the sending system. The receive window represents the number of bytes that are available in the receive buffer. If the buffer is full, the receiving system advertises a receive window sizeof zero, and the sending system must wait to send more data. After the receiving application retrieves data from the receive buffer, the receiving system can then advertise a receive window size that is equal to he amount of data that was read. Then, TCP on the sending system can resume sending data.

The available space in the receive buffer depends on how quickly data is read from the buffer by the receiving application. TCP keeps the data in its receive buffer. After the receiving application reads the data, that space in the buffer is available for new data. The amount of free space in the buffer is advertised to the sending system, as described in the previous paragraph. 