---
tags:
  - CS446
aliases:
  - Interrupt
---
interrupts (or hardware interrupts) are caused by an external event (asynchronous)
- some device finishes input/output, timer expires, HID user input, etc.

## Polling
have CPU periodically check if each device needs service
issues:
- consumes CPU time even when there are no events pending
- trying to reduce checking frequency leads to longer response times

## Device Interrupt Request (IRQ) Lines
give each device access to interrupt the CPU
- each device can be connected to an interrupt request line
issues 
- non-flexible handling of interrupts ("hardcoded")
- CPU might get interrupted non-stop
- a device may overwhelm CPU
- critical interrupts can be delayed

## Programmable Interrupt Controller (PIC)
responsible for telling the CPU when and which device wishes to "interrupt"
- input/output devices have (unique or shared) IRQs
- IRQs are mapped by the PIC hardware to interrupt vectors and passed to the CPU
	- interrupt vector: each entry of the interrupt descriptor/vector table

## Interrupt Descriptor/Vector Table
a data structure to associate interrupt requests with handlers
- each entry called an interrupt vector
	- specifies memory address of handler routine
- architecture-specific implementation

note: in x86 called interrupt descriptor table
- architecture supports $256$ interrupts, so the interrupt descriptor table contains $256$ entries
- each entry specifies the address of the handler plus some flags
- can be programmed by the [[Operating systems|Operating system]]
	- e.g. in Pintos: `make_intr_gate` (src/threads/interrupt.c)