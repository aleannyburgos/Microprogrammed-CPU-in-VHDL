# Microprogrammed CPU – ECE 495 Lab 7

## Overview
This project implements a **Microprogrammed CPU** on the **Altera DE2-115 FPGA board** using **VHDL** and structural modeling.  
The CPU architecture includes a custom microsequencer, micro-ROM, RAM, and an 8-bit datapath supporting instruction fetch, decode, execution, stack operations, arithmetic, branching, and halting.

This design follows the NJIT **ECE 495 – Experiment 7** specifications. The instrucrtion set was given and the rtl statements were derived as well as the CPU Block diagram.

---

## CPU Architecture
The CPU consists of:

- Program Counter (PC) – 8-bit  
- Instruction Register (IR) – 8-bit  
- Memory Address Register (MAR) – 8-bit  
- Memory Data Register (MDR) – 8-bit  
- Register File – R0 & R1 (8-bit each)  
- Stack Pointer (SP) – 8-bit  
- Condition Flag (Z) – 1-bit  
- Custom Microsequencer + Micro-ROM  
- External RAM (lpm_ram_dq)

---

## Instruction Set
Supported Instructions:

| Instruction | Description |
|-----------|------------|
| NOP | No operation |
| LOADI Rn, X | Load immediate |
| LOAD Rn, X | Load from memory |
| STORE X, Rm | Store to memory |
| MOVE Rn, Rm | Register move |
| ADD / SUB | Arithmetic |
| TESTNZ / TESTZ | Condition flag operations |
| JUMP | Unconditional jump |
| JUMPZ | Conditional jump if Z = 1 |
| LOADSP X | Load stack pointer |
| PEEP | Read from top of stack |
| PUSH / POP | Stack operations |
| HALT | Stop CPU execution |

Instructions are either **1-byte or 2-byte**.
The first byte always contains the opcode.

---

## Implementation Details
- Written in **VHDL**
- Uses **lpm_counter** for PC and SP
- Uses **lpm_ff** for registers
- RAM implemented using **lpm_ram_dq**
- Microsequencer source provided by course
- Micro-ROM programmed via `.mif` file

---

## Testing & Display Requirements
During execution, the following must be displayed:

- R0 and R1 values  
- PC value  
- SP value  
- Z Flag (LED)  
- Additional registers if needed for debugging  

Seven-segment display or LCD may be used.

---

## Running the Project
1. Open the Quartus project
2. Load all VHDL source files
3. Compile the design
4. Program the DE2-115 FPGA board
5. Load RAM test `.mif` file
6. Load micro-ROM `.mif` file

---

## Deliverables
- CPU Block Diagram
- CPU vhdl code
- f25lab7_seq
- Seven Segment Decoder

---
