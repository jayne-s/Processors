# Processors 

**Course:** CE 4304 - Computer Architecture\
**Semester:** Spring 2024\
**Project:** Processors (Harvard Architecture)\
**Language:** Verilog

## Overview

This project involves the design and implementation of a custom Instruction Set Architecture (ISA) 
and a single-cycle, multi-cycle, and pipelined processor that executes it. The processor is tailored for embedded systems and 
follows a Harvard architecture, with separate instruction and data memories. The project was completed in 
two phases: 1) ISA design and specification 2) processor implementation and simulation in Verilog. The final
design is capable of executing arithmetic operations and control-flow logic required to run simple programs, 
including loop-based computation.

## Processor Specifications

| **Feature** | **Specification** |
| --------- | --------------- |
| Target Market | Embedded Systems |
| Architecture | Harvard |
| Address Bus Width | 11 bits |
| Address Space | 2048 Addresses | 
| Program Entry Point | 0x400 |
| Data Width | 24 bits |
| Instruction Width | 23 bits |
| Immediate Field | 12 bits |
| Instruction Types | 5 bits (up to 32 instructions) |
| Register File | 4 x 24-bit registers |
| Register Address Width | 2 bits |
| Endianness | Little Endian | 

## Instruction Set Architecture (ISA)

* Custom-designed 23-bit instruction format
* Supports: arithmetic operations, immediate-based instructions, control flow and branching
* Inspired by RISC-style architectures
* Instruction Fields: Opcode (5 bits), Register Operands (2-bit addressing), Immediate Field (12 bits)

## Supported Programs

### Arithmetic Operation 

``` C = A + B ```

### Loop-Based Accumulation

```
int sum = 0;
for (i = 0; i <=10; i++) {
 sum += i;
}
```

## Sample Input

TO BE UPDATED

## Sample Output

TO BE UPDATED

## Simulation and Testing

* Simulated using EDA Playground.
* Instruction memory initialized with machine code starting at address 0x400
* Waveforms inspected to verify correct state transitions, register updates, program counter behavior, instruction execution timing.

## Possible Extensions

* Expanded Instruction Set
* Interrupt Handling
* Cache Integration
* FPGA Synthesis and Deployment
