---
tags:
  - CS446
---
timers are critical for an [[Operating systems|Operating system]]

fallback mechanism for operating system to reclaim control over the machines's operation
- timer is set to generate an [[Interrupts|Interrupt]] periodically
- setting the timer is a privileged instruction
- when timer expires, generates an interrupt
- handles by kernel, which controls resumption context
	- basis for operating system schedular

prevents infinite loops
- operating system should always be able to regain control from erroneous or malicious programs hogging CPU

used for time-based functions
- e.g. `sleep()`