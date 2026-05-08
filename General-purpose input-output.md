---
tags:
  - CPE301
---
A general-purpose input/output (GPIO) is an uncommitted digital signal pin on an integrated circuit or electronic circuit board which may be used as an input or output, or both, and is controllable by software.

GPIOs have no predefined purpose and are unused by default. If used, the purpose and behaviour of a GPIO is defined and implemented by the designer of higher assembly-level circuitry: the circuit board designer in the case of integrated circuit GPIOs, or system integrator in the case of board-level GPIOs.

## Arduino ATMEGA2560 GPIO Modes

|      OUTPUT      | DDR |   PORT   |   PIN   |
|:----------------:|:---:|:--------:|:-------:|
|      INPUT       |  1  | DATA OUT |   N/A   |
| INPUT w/ Pull-up |  0  |    0     | DATA IN |
|                  |  0  |    1     | DATA IN |

