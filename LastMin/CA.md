# Computer Architecture (COA)

Computer Architecture defines how a computer’s components communicate through electronic signals to perform input, processing, and output operations. It covers the design and organization of the CPU, memory, storage, and input/output devices. It describes how these components interact through buses, control signals, and data pathways, directly influencing the speed, functionality, and reliability of a computer system.

---

## Basic Terminology

### Control Unit (CU)
The Control Unit handles all processor control signals. It directs input and output flow, fetches instructions, and controls how data moves around the system.

### Arithmetic and Logic Unit (ALU)
The ALU performs arithmetic operations such as addition and subtraction, logical operations like AND, OR, NOT, bit shifting, and comparisons.

### CPU Registers (Main Memory Unit)
- **Accumulator (AC):** Stores results produced by the ALU  
- **Program Counter (PC):** Holds the address of the next instruction  
- **Memory Address Register (MAR):** Stores memory addresses for read/write operations  
- **Memory Data Register (MDR/MBR):** Holds data fetched from or sent to memory  
- **Current Instruction Register (CIR):** Stores the current instruction  
- **Instruction Buffer Register (IBR):** Stores instructions not executed immediately  

### Input / Output Devices
Input devices load programs or data into memory, while output devices display or store results under CPU control.

---

## Buses

Buses connect all major components of the computer.
- **Data Bus:** Transfers actual data  
- **Address Bus:** Transfers memory addresses  
- **Control Bus:** Transfers control and status signals  

---

## Types of Computer Architecture

### Von Neumann Architecture
Uses a single memory for both data and instructions. Instructions and data are fetched sequentially. This design is simple and widely used.

### Harvard Architecture
Uses separate memories for data and instructions. Allows parallel access and higher speed. Common in embedded systems.

---

## Instruction Set and Formats

Instruction formats depend on the number of addresses:
- Zero Address
- One Address
- Two Address
- Three Address

CPU organizations:
- Single Accumulator Organization
- General Register Organization
- Stack Organization

---

## Machine Instructions

### Types
- **Data Transfer:** LOAD, STORE, MOVE  
- **Arithmetic:** ADD, SUB, MUL, DIV  
- **Logical:** AND, OR, NOT, XOR  
- **Control Transfer:** JUMP, CALL, RET  
- **Input/Output:** IN, OUT  
- **Shift & Rotate:** SHL, SHR, ROL, ROR  

---

## Components of an Instruction
- **Opcode:** Specifies operation  
- **Operands:** Data or addresses involved  

---

## Addressing Modes

- Immediate: Operand in instruction (ADD R1, 5)  
- Register: Operand in register (ADD R1, R2)  
- Direct: Address given directly (LOAD R1, 1000)  
- Indirect: Address stored elsewhere (LOAD R1, (R2))  
- Register Indirect: Register holds address  
- Indexed: Base + index  
- Base Addressing: Base register + offset  
- Relative: PC + offset  
- Implicit: Operand implied  

**Effective Address = displacement + base + index**

---

## RISC vs CISC

RISC uses fixed-size instructions, hardwired control, more registers, low power, high pipelining, and single-cycle execution.  
CISC uses variable-size instructions, complex addressing modes, fewer registers, higher power usage, and multi-cycle execution.

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
- Status / Flag Register  

---

## Flag Register

- **Zero (Z):** Result is zero  
- **Carry (CY):** Carry generated  
- **Parity (P):** Even parity  
- **Auxiliary Carry (AC):** Carry between nibbles  
- **Sign (S):** MSB indicates sign  

---

## Instruction Cycle

1. Fetch  
2. Indirect (if required)  
3. Execute  
4. Interrupt  
5. Store (Write Back)  

---

## Control Unit

### Hardwired Control Unit
Uses fixed logic, faster operation, used in RISC processors.

### Microprogrammed Control Unit
Uses control memory, flexible but slower.

Types:
- Horizontal microprogramming
- Vertical microprogramming

---

## Microprogram Concepts

- **Microprogram:** Sequence of microinstructions  
- **Microinstruction:** Control word + sequencing word  
- **Micro-operations Example:**  
t1: MAR ← PC  
t2: MBR ← Memory, PC ← PC + 1  
t3: IR ← MBR  

---

## Memory Organization

Memory is composed of registers. Each register is a memory location identified by an address. Memory capacity is the total number of bits it can store.

### Byte vs Word Addressable Memory
Byte addressable memory stores 8-bit cells, while word addressable memory stores CPU word-sized cells.

---

## Memory Hierarchy

1. Registers  
2. Cache Memory  
3. Main Memory  
4. Secondary Storage  

---

## Cache Memory

Cache is high-speed memory used to bridge the speed gap between CPU and main memory.

### Locality of Reference
- **Temporal Locality:** Recently used data reused soon  
- **Spatial Locality:** Nearby data accessed soon  

### Cache Mapping
- Direct Mapping  
- Associative Mapping  
- Set-Associative Mapping  

---

## Multilevel Cache

- **L1:** Smallest and fastest  
- **L2:** Larger and slower than L1  
- **L3:** Shared among cores  

---

## Cache Performance

- **Hit Ratio = Hits / Total Accesses**  
- **Miss Ratio = 1 − Hit Ratio**

EMAT (2-level cache):  
EMAT = H1×T1 + (1−H1)[H2×T2 + (1−H2)×TM]

---

## Cache Replacement Policies

- LRU  
- FIFO  
- Random  
- LFU  
- Optimal  

---

## Cache Update Policies

### Write Through
Updates cache and main memory simultaneously.

### Write Back
Updates cache first and writes to memory only if dirty bit is set.

---

## Cache Miss Types

- Compulsory Miss  
- Conflict Miss  
- Capacity Miss  

---

## I/O Interface

Connects CPU and memory with external devices.

### Data Transfer Modes
- Programmed I/O  
- Interrupt Driven I/O  
- Direct Memory Access (DMA)  

---

## DMA Transfer Modes

- Burst Mode  
- Cycle Stealing Mode  

---

## Pipelining

Pipelining allows overlapping execution of instructions to improve performance.

### RISC 5-Stage Pipeline
1. Instruction Fetch  
2. Instruction Decode  
3. Execute  
4. Memory Access  
5. Write Back  

### Speedup
S = (n × k) / (k + n − 1)

---

## Pipeline Hazards

### Structural Hazards
Resource conflicts.

### Data Hazards
RAW, WAR, WAW.

### Control Hazards
Caused by branch instructions.

Solutions include forwarding, stalls, and branch prediction.

---

## IEEE 754 Floating Point Standard

Components:
- Sign Bit  
- Biased Exponent  
- Normalized Mantissa  

Formats:
- Single Precision (32-bit)  
- Double Precision (64-bit)  

Special Case:
E = 0 and M = 0 represents Zero.
