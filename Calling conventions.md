---
tags:
  - CS446
---
a standard on how functions should be implemented and called by the machine
- how a function call in c or c++ gets converted into [[Assembly language]]
	- how arguments are passed to a function, how return values are passed back out of a function, how the function is called, and how the function manages the [[Stacks|Stack]] and its stack frame, etc.
- compilers need to obey this standard when compiling code into assembly
	- set up the stack and CPU registers properly

why?
- a program calls functions across many object files and libraries
	- to be able to interface all of these, we need a standardisation for how function calls take place

registers divided into two groups:
- caller-saved/volatile regs: hold temporary quantities that need not be preserved across calls, i.e., their values aren't assumed to be required after the next function call returns
	- caller's responsibility to push these registers onto the stack or copy them somewhere else if it wants to restore these values after a procedure `call` 
	- considered normal for a `call` to "clobber" temporary values in these regs, i.e., the callee function is free to modify these
		- on x86, `%eax`, `%edx`, `%ecx`
- callee-saved/non-volatile regs: caller expects these to hold the same value after `call`
	- callee's responsibility to restore these to their original values before returning to the caller, or to ensure it doesn't touch them 
		- on x86, `%ebx`, `%esi`, `%edi`, `%edp`, `%esp`