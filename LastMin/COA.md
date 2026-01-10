# Computer Organization and Architecture (COA)

## Introduction
Computer architecture defines how a computer’s components communicate through electronic signals to perform input, processing, and output operations.

It covers:
- Design and organization of CPU, memory, storage, and input/output devices  
- Interaction through buses, control signals, and data pathways  
- Influence on speed, functionality, and reliability of a computer system  

---

## Basic Terminology

### Control Unit (CU)
- Handles all processor control signals  
- Directs input and output flow  
- Fetches instructions  
- Controls movement of data within the system  

### Arithmetic and Logic Unit (ALU)
- Performs arithmetic operations (ADD, SUB, MUL, DIV)  
- Performs logical operations (AND, OR, NOT, XOR)  
- Performs bit shifting operations  

---

## Main Memory Unit (Registers)

- **Accumulator (AC)**: Stores results of ALU operations  
- **Program Counter (PC)**: Stores address of the next instruction  
- **Memory Address Register (MAR)**: Holds memory address to be accessed  
- **Memory Data Register (MDR / MBR)**: Holds data transferred to/from memory  
- **Current Instruction Register (CIR / IR)**: Stores current instruction  
- **Instruction Buffer Register (IBR)**: Holds instruction waiting for execution  

---

## Input / Output Devices
- Input devices read data/programs into memory  
- Output devices display processed results  
- Operate under CPU control  

---

## Buses

### Types of Buses
- **Data Bus**: Transfers data  
- **Address Bus**: Transfers addresses  
- **Control Bus**: Transfers control and status signals  

---

## Types of Computer Architecture

### Von Neumann Architecture
- Single memory for data and instructions  
- Sequential access  
- Simple design  

### Harvard Architecture
- Separate memory for data and instructions  
- Parallel access  
- Faster execution  
- Used in embedded systems  

---

## Instruction Set and Addressing Modes

### Instruction Formats
- Zero Address  
- One Address  
- Two Address  
- Three Address  

### CPU Organization
- Single Accumulator Organization  
- General Register Organization  
- Stack Organization  

---

## Machine Instructions

### Data Transfer Instructions
- LOAD, STORE, MOVE  

### Arithmetic Instructions
- ADD, SUB, MUL, DIV  

### Logical Instructions
- AND, OR, NOT, XOR  

### Control Transfer Instructions
- JUMP, CALL, RET  

### I/O Instructions
- IN, OUT  

### Shift and Rotate Instructions
- SHL, SHR, ROL, ROR  

---

## Components of an Instruction
- **Opcode**: Specifies operation  
- **Operands**: Data or addresses involved  

---

## Addressing Modes

| Addressing Mode | Description | Example |
|-----------------|-------------|---------|
| Immediate | Operand in instruction | ADD R1, 5 |
| Register | Operand in register | ADD R1, R2 |
| Direct | Address specified directly | LOAD R1, 1000 |
| Indirect | Address stored elsewhere | LOAD R1, (R2) |
| Register Indirect | Register holds address | LOAD R1, (R3) |
| Indexed | Base + index | LOAD R1, 1000(R2) |
| Base | Base register + offset | LOAD R1, 200(RB) |
| Relative | PC + offset | JUMP 200 |
| Implicit | Operand implied | CLR |

---

## RISC vs CISC

| Feature | RISC | CISC |
|-------|------|------|
| Instruction size | Fixed | Variable |
| Control unit | Hardwired | Hardwired + Microprogrammed |
| Registers | More | Less |
| Addressing modes | Simple | Complex |
| Power | Low | High |
| Pipelining | High | Low |

---

## CPU Registers
- Program Counter (PC)  
- Instruction Register (IR)  
- Memory Address Register (MAR)  
- Memory Data Register (MDR)  
- Accumulator (AC)  
- General Purpose Registers (GPR)  
- Temporary Register (TR)  
- Stack Pointer (SP)  
- Flag Register  

---

## Flag Registers
- Zero (Z)  
- Carry (CY)  
- Parity (P)  
- Auxiliary Carry (AC)  
- Sign (S)  

---

## Instruction Cycle
1. Fetch  
2. Decode  
3. Execute  
4. Store  
5. Interrupt  

---

## Control Unit

### Hardwired Control Unit
- Fixed logic circuits  
- Faster  
- Used in RISC  

### Microprogrammed Control Unit
- Control signals stored in memory  
- Slower  
- Flexible  

---

## Memory Organization
- Memory consists of registers  
- Each register has a unique address  
- Capacity = total bits stored  

### Addressable Memory
- Byte Addressable  
- Word Addressable  

---

## Memory Hierarchy
- Registers  
- Cache  
- Main Memory  
- Secondary Storage  

---

## Cache Memory

### Locality of Reference
- Temporal Locality  
- Spatial Locality  

### Cache Mapping
- Direct Mapping  
- Associative Mapping  
- Set-Associative Mapping  

---

## Cache Performance
- Hit Ratio = Hits / Total Accesses  
- Miss Ratio = 1 − Hit Ratio  

---

## Cache Replacement Policies
- LRU  
- FIFO  
- LFU  
- Random  
- Optimal  

---

## Cache Write Policies

### Write Through
- Write to cache and memory  

### Write Back
- Write to cache only  
- Update memory later  

---

## Cache Miss Types
- Compulsory Miss  
- Conflict Miss  
- Capacity Miss  

---

## I/O Interface
- Connects CPU with external devices  
- Manages data transfer  

### I/O Modes
- Programmed I/O  
- Interrupt Driven I/O  
- DMA  

---

## DMA (Direct Memory Access)

### DMA Transfer Modes
1. Burst Mode  
2. Cycle Stealing Mode  

---

## Pipelining
- Overlapping execution of instructions  
- Improves throughput  

### RISC Pipeline Stages
1. Instruction Fetch  
2. Instruction Decode  
3. Execute  
4. Memory Access  
5. Write Back  

---

## Pipeline Hazards

### Structural Hazard
- Resource conflict  

### Data Hazard
- RAW  
- WAR  
- WAW  

### Control Hazard
- Branch instructions  

---

## IEEE 754 Floating Point Standard

### Components
- Sign Bit  
- Biased Exponent  
- Normalized Mantissa  

### Formats
- Single Precision (32-bit)  
- Double Precision (64-bit)  

