# Multicycle Processor 

**Course:** CE 4304 - Computer Architecture\
**Semester:** Spring 2024\
**Project:** Multicycle Processor (Harvard Architecture)\
**Language:** Verilog

## Overview

This project involves the design and implementation of a custom Instruction Set Architecture (ISA) 
and a multi-cycle processor that executes it. The processor is tailored for embedded systems and 
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

## Network Model

* **Topology:** Star
* **Message Delay:** 1 unit of distance = 1 unit of simulation time
* **RTT Calculation:** RTT = time received - time sent
* **Assumptions:**
  * Host only pings one destination
  * Ping interval is always greater than RTT
  * Input file is complete and valid
  * Event processing order is time based

## How the Simulation Works

* Read input file
* Create hosts and neighbor relationships
* Bootstrap ping events
* Run simulation loop
  * Pop next event from the FutureEventList
  * Call handle() on the event
  * Continue until no events remain 

## Sample Input
```
5
6 2
7 3
-1
5 7 10 28
```
* First number is the central host address
* Following lines are of the format: ```<neighbor address> <distance>```
* -1 terminates list of neighbors
* Following lines are of the format: ```<source> <destination> <interval> <duration>```

## Sample Output
```
[10ts] Host 5: Sent ping to host 7
[13ts] Host 7: Ping request from host 5
[16ts] Host 5: Ping response from host 7 (RTT = 6ts)
[20ts] Host 5: Sent ping to host 7
[23ts] Host 7: Ping request from host 5
[26ts] Host 5: Ping response from host 7 (RTT = 6ts)
[28ts] Host 5: Stopped sending pings
```
* ```ts```= simulation time units
* Output ordering may differ when multiple events occur at the same time

## How to Run

* Place ```simulation.txt``` in the project root directory.
* Compile: ```javac *.java```
* Run: ```java Main```

## Possible Extensions

* Expanded Instruction Set
* Interrupt Handling
* Cache Integration
* FPGA Synthesis and Deployment
