---
tags:
  - CPE201
---
Shift registers are sequential logic circuits that are used for the storage or transfer of binary data. Shift registers come in two flavours: [[Parallel shift registers]] and [[Serial shift registers]]. Parallel shift registers use $2$ or more transfer lines to input or output all data bits simultaneously. Serial shift registers are limited to $1$ transfer line and can only input or output one data bit at a time.

## Serial In / Serial Out
SISO shift registers are the most basic. Data bits are loaded and unloaded one bit at a time in either a positive or negative direction under clock control.

## Serial In / Parallel Out
SIPO shift registers are loaded with serial data, one bit at a time and unloaded with parallel data. 

## Parallel In / Serial Out
PISO shift registers are loaded with parallel data and unloaded with serial data. PISO shift registers are the most complex shift registers as they require additional data-input lines with $\text{ SHIFT }$ and $\text{ LOAD }$ operations.

## Parallel In / Parallel Out
PIPO shift registers are loaded and unloaded with parallel data. PIPO shift registers are the fastest but most expensive type of shift register.

