---
tags:
  - CS219
---
Instruction pipelining is a technique for implementing [[Instruction-level parallelism]] within a single processor. Pipelining attempts to keep every part of the processor busy with some instruction by dividing incoming instruction into a. series of sequential steps performed by different [[Processor units]] with different parts of instructions processed in parallel.

The classic RISC pipeline comprises:
1. $[ \text{ IF } ]$ Instruction fetch
2. $[ \text{ ID } ]$ Instruction decode and register fetch
3. $[ \text{ EX } ]$ Execute
4. $[ \text{ MEM } ]$ Memory access
5. $[ \text{ WB } ]$ Register write back

## Hazards
The model of sequential execution assumes that each instruction completes prior to the next. This assumption is not true on a pipelined processor. A situation where the expected result is problematic is known as a hazard.

### Solutions
Pipelined processors use three techniques to work as expected when the programmer assumes that each instruction completes before the next one begins.
- The pipeline could stall, or cease scheduling new instructions until the required values are available. This results in empty slots in the pipeline, or bubbles, in which no work is performed.
- An additional data path can be added that routes a computed value to a future instruction elsewhere in the pipeline before the instruction that produced it has been fully retired, a process called [[Operand forwarding]].
- The processor can locate other instructions which are not dependent on the current ones and which can be immediately executed without hazards, an optimisation known as [[Out-of-order execution]].