---
tags:
  - CS219
---
Volatile memory, in contrast to [[Non-volatile memory]], is computer memory that retains its contents only when powered.

Volatility can protect sensitive information, as it becomes unavailable on power-down. Most general-purpose [[Random-access memory]] is volatile.

## Types
[[Dynamic random-access memory]] stores each bit of information in a different capacitor within the integrated circuit. DRAM chips need just one single capacitor and one transistor to store each bit of information. This makes it space-efficient and inexpensive.

[[Static random-access memory]] does not need continuous electrical refreshes, but it still requires constant [[Electric current]] to sustain the difference in [[Electric voltage]]. Each bit in a SRAM chip needs a cell of six transistors. As a result, SRAM is unable to accomplish the storage capabilities of the DRAM family. SRAM is commonly used as CPU cache and for processor registers and in networking devices.