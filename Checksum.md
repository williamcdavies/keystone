---
tags:
  - CPE400
---
A checksum is a small-sized block of data derived from another block digital data for the purpose of detecting errors that may have been introduced during its transmission or storage.

The procedure which generates this checksum is called a checksum function or checksum algorithm.

## Algorithms

### Parity Byte or Parity Word
The simplest checksum algorithm is the so-called longitudinal parity check, which breaks the data into words with a fixed number $n$ of bits, and then computes the $\text{ XOR }$ of all those words. The result is appended to the message as an extra word.

### Sum Complement
A variant of the previous algorithm is to add all the "words" as unsigned binary numbers, discarding any overflow bits, and append the [[Two's complement]] of the total as the checksum.

## IP Checksums

### [[Transmission control protocol (TCP)]] Checksum
Checksum calculated over an IP "pseudo-header" and the actual TCP data.

1. The IP pseudo-header is the source address, destination address, protocol (padded with a zero byte), TCP length and $8$-bit reserved field ($8$-bit of zeroes for padding purpose).
2. Next, we add the entire TCP datagram, treating it all as $16$-bit quantities and skipping the checksum (treating it as all zeroes).
3. Addition of $16$-bit contents and then take [[One's complement]].
4. Sender puts checksum value into TCP checksum field.

### [[User datagram protocol (UDP)]] Checksum
Checksum calculated over an IP "pseudo-header" and the actual UDP data.

1. The IP pseudo-header is the source, address, destination address, protocol (padded with a zero byte), and UDP length.
2. Next, we add the entire UDP datagram, treating it all as $16$-bit quantities and skipping the checksum (treating it as all zeroes).
3. Addition of $16$-bit contents and then take one's complement.
4. Sender puts checksum value into UDP checksum field.
5. Receiver does the exact same thing upon receiving the packet but uses checksum value as-is.

