# Operating System (OS)

An **Operating System (OS)** is a system software that manages computer hardware, software resources, and provides common services for computer programs. It acts as an interface between the user and the computer hardware.


---

## Types of Operating System (OS)

### Batch OS

* Executes a set of similar jobs together.
* CPU processes one job at a time; next job starts only after the previous finishes.

### Multiprogramming OS

* Multiple jobs are loaded in memory.
* CPU switches to another job when one is waiting (e.g., for I/O).
* Keeps CPU always busy.

### Time-Sharing / Multitasking OS

* A type of multiprogramming where each process gets a fixed time slice (quantum).
* CPU switches between tasks quickly so all users/processes feel simultaneous execution.

### Multiprocessing OS

* Uses more than one CPU for executing processes.
* Improves system throughput.

### Multi-user OS

* Allows multiple users to work at the same time.
* Can run on single or multiple processors.

### Distributed OS

* Manages a group of interconnected computers that communicate over a network.
* Each system has its own CPU and memory, but works as a single system.

### Network OS

* Runs on a server to manage files, users, security, and applications over a network.
* Allows shared access to resources like printers and files.

### Real-Time OS (RTOS)

* Designed for dedicated tasks with strict deadlines.
* Common in embedded systems, medical devices, and industrial machines.

---

## Threads

**Definition:** A thread is a lightweight process and the basic unit of CPU execution.

### Features

* Has its own program counter, registers, and stack.
* Shares code, data, files, and signals with other threads of the same process.

**Creation:** Using `fork()` system call.

A process with `n` fork() calls creates **2ⁿ − 1 child processes**.

### Types of Threads

**Based on number:**

* Single-threaded process
* Multi-threaded process

**Based on level:**

* User-level threads
* Kernel-level threads

**Examples:** Java Threads, POSIX Threads, Windows Threads, Solaris Threads

read more about - Threads

---

## Process

A **process** is a program in execution.

### Key Points

* Program Counter (PC) points to the next instruction to execute.
* Represented internally by **Process Control Block (PCB)**.
* Can contain one or more threads.

### Process States Diagram

state

---

## Schedulers

The OS uses schedulers to manage which process gets CPU time.

### Long-term Scheduler

* Controls admission of new processes into main memory.
* Transitions processes from **New → Ready** state.

### Medium-term Scheduler

* Temporarily suspends or resumes processes.
* Performs **swap-out** (main → secondary memory) and **swap-in** (secondary → main memory).

### Short-term Scheduler

* Selects a process from the ready queue for execution.
* Transitions processes from **Ready → Running** state.

### Dispatchers

* Responsible for loading the selected process onto the CPU.

Performs **context switching**:

* Saves the state of the current process.
* Loads the state of the next process to execute.

---

## CPU Scheduling Algorithms

### Why Scheduling is Needed

* Processes involve CPU time and I/O time.
* In uniprogramming, CPU sits idle during I/O waits.
* Multiprogramming allows CPU to execute another process while one waits for I/O.
* Scheduling decides which process gets the CPU and when.

### Process Timing Terms

**Arrival Time (AT):** When the process enters the ready queue.

**Completion Time (CT):** When the process finishes execution.

**Burst Time (BT):** Time needed by CPU to execute the process.

**Turnaround Time (TAT):** Total time process spends in the system.

Formula:

```
TAT = CT − AT
```

**Waiting Time (WT):** Total time process waits in the ready queue.

Formula:

```
WT = TAT − BT
```

### Objectives of Process Scheduling Algorithm

* Max CPU utilization
* Fair allocation of CPU
* Max throughput
* Min turnaround time
* Min waiting time
* Min response time

---

## Different CPU Scheduling Algorithms

### 1. First Come First Serve (FCFS)

First Come, First Serve (FCFS) is one of the simplest types of CPU scheduling algorithms. It works exactly as its name suggests: the process that arrives first in the ready queue is executed first, similar to a queue at a grocery store.

* It is a **non pre-emptive** algorithm.
* Processes are assigned to the CPU based on their **arrival time**.
* If two or more processes have the same arrival time, they are scheduled based on **process ID**.
* It is **free from starvation**, but can suffer from long waiting times.

### 2. Shortest Job First (SJF)

Shortest Job First (SJF), also called Shortest Job Next (SJN), selects the process with the **smallest burst time** to execute next.

* It is a **non-pre-emptive** algorithm.
* If all processes have equal burst time, it behaves like FCFS.
* Burst time must be known before execution.
* Minimizes average response time.
* Can cause **starvation** for long processes.

### 3. Shortest Remaining Time First (SRTF)

SRTF is the **pre-emptive** version of SJF where scheduling is based on the **shortest remaining burst time**.

* Pre-emptive algorithm.
* If all arrival times are equal, behaves like SJF.
* Minimizes average turnaround time.
* Long processes may starve if short processes keep arriving.

### 4. Round Robin (RR)

Round Robin scheduling is designed for time-sharing systems where each process is assigned a **time quantum**.

* Pre-emptive FCFS-based algorithm.
* Small time quantum → more context switching.
* Large time quantum → behaves like FCFS.
* Balances response time and throughput.

### 5. Priority Scheduling

Processes are scheduled based on **priority**.

* Can be pre-emptive or non-pre-emptive.
* Higher priority process executes first.
* Equal priority → FCFS behavior.
* Can cause starvation for low-priority processes.

### 6. Highest Response Ratio Next (HRRN)

Processes are scheduled based on **highest response ratio**, which avoids starvation.

* Non pre-emptive algorithm.
* Favors short jobs while limiting waiting time of long jobs.

Response Ratio formula:

```
Response Ratio = (WT + BT) / BT
```

---

## Critical Section Problem

**Critical Section:** Part of program where shared variables are accessed.

**Remainder Section:** Remaining program excluding CS.

**Race Condition:** Output depends on execution order.

### Requirements for Correct Solution

* Mutual Exclusion
* Progress
* Bounded Waiting

---

## Synchronization Tools

### Semaphore

* Integer variable
* Uses atomic operations
* Prevents race condition

### Atomic Operations

* No pre-emption
* No interference

```
wait()   // P()
signal() // V()
```

### Types of Semaphores

**Counting Semaphore**

* Value ranges over integers
* Used for multiple instances

**Mutex**

* Provides mutual exclusion
* Only one process in CS

Misconception: Mutex ≠ Binary Semaphore

read more about - Critical Section Problem

---

## Deadlock

Deadlock occurs when:

* Each process holds at least one resource
* Each waits for another resource

### Necessary Conditions

* Mutual Exclusion
* Hold and Wait
* No Preemption
* Circular Wait

### Deadlock Handling

**Prevention, Avoidance, Detection & Recovery, Ignorance**

### Banker’s Algorithm

Data Structures:

* Available
* Max
* Allocation
* Need

Formula:

```
Need = Max − Allocation
```

### Deadlock Detection and Recovery

* Detection: Resource allocation graph / safety algorithm
* Recovery: Process termination, resource pre-emption

### Deadlock Ignorance

* Ostrich Algorithm
* Reboot system

read more about - Deadlock

---

## Memory Management

Memory management subdivides memory among processes to minimize fragmentation.

### Why Memory Management is Required

* Allocate/de-allocate memory
* Track memory usage
* Minimize fragmentation
* Ensure data integrity

### Logical vs Physical Address

**Logical Address:** Generated by CPU (Virtual)

**Physical Address:** Actual address in memory

### Static and Dynamic Loading

**Static Loading:** Entire program loaded at once

**Dynamic Loading:** Routine loaded only when called

---

## Memory Management Techniques

### Single Partition Allocation

* OS + User memory

### Multiple Partition Allocation

* Fixed Partition
* Variable Partition

### Variable Partition Allocation

* First Fit
* Best Fit
* Worst Fit

Note: Best fit is not always optimal

---

## Paging

* Fixed-size frames and pages
* Page size = Frame size

paging

## Segmentation

* User view of memory
* Logical address space divided into segments

---

## Page Fault

Occurs when required page is not in memory.

---

## Page Replacement Algorithms

### 1. First In First Out (FIFO)

FIFO replaces the **oldest loaded page** in memory.

Example:
Page reference string: `1, 3, 0, 3, 5, 6` with 3 frames

* Initial loads cause page faults
* Oldest page is replaced first

**Belady’s Anomaly:** Increasing frames can increase page faults in FIFO.

### 2. Optimal Page Replacement

Replaces the page that will **not be used for the longest time in the future**.

* Produces minimum page faults
* Not implementable practically
* Used as benchmark

### 3. Least Recently Used (LRU)

Replaces the page that was **least recently accessed**.

* Practical approximation of optimal
* Requires tracking recent usage

### 4. Most Recently Used (MRU)

Replaces the page that was **most recently used**.

* Opposite of LRU
* Can suffer from Belady’s anomaly

read more about - Page Replacement Algorithms

---

## Virtual Memory

* Uses disk as extension of RAM
* Allows large programs
* Based on paging

virtual_memory

### Demand Paging

* Pages loaded only when required
* Causes page fault

**Advantages**

* Better RAM utilization
* Faster startup

read more about - Demand Paging

---

## Thrashing

* Excessive paging activity

### Causes

* Too many processes
* Insufficient RAM

### Effects

* Low CPU utilization
* Slow system

### Handling Techniques

* Reduce multiprogramming
* Working set model
* Increase RAM

read more about - Virtual Memory

---

## File Systems

A file system organizes and manages files.

### File Directory Information

* Name
* Type
* Address
* Length
* Owner ID
* Protection

### Directory Operations

* Search
* Create
* Delete
* List
* Rename
* Traverse

### File Allocation Methods

**Continuous Allocation**

* Contiguous blocks

**Linked Allocation**

* Non-contiguous

**Indexed Allocation**

* Index block

read more about - File Systems

---

## Disk Scheduling

### Algorithms

* FCFS
* SSTF
* SCAN
* C-SCAN
* LOOK
* C-LOOK
* LIFO
