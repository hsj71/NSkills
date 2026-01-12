# Computer Networks

A **computer network** is a system of interconnected computing devices that communicate with one another over wired or wireless communication links to exchange data, share resources, and deliver services, using a well-defined set of communication protocols.

Computer networks form the foundation of modern communication systems, including the Internet, cloud services, and distributed applications.

**aa.webpaa.webp**

---

## Objectives of Computer Networks

The main goals of computer networking are:

* **Resource Sharing** – sharing hardware (printers, storage), software, and data
* **Communication** – email, messaging, video conferencing
* **Reliability** – backup paths and fault tolerance
* **Scalability** – easy expansion as the number of users grows
* **Cost Efficiency** – reduced cost through shared infrastructure

---

## Basics of Computer Networks

### Network Components

Every computer network consists of the following fundamental components:

* **Sender (Source)** – device that generates data
* **Receiver (Destination)** – device that receives data
* **Message** – information being transmitted
* **Transmission Medium** – physical or wireless path for data transfer
* **Protocol** – set of rules governing communication

---

## Network Topologies

Network topologies refer to the physical or logical arrangement of devices (nodes) and communication links in a computer network. They define how devices are connected to each other and how data flows within the network.

There are different topologies which are used in computer networks:

---

### Mesh Topology

* Every device is directly connected to every other device using a dedicated communication link.
* For **N** devices, the total number of links required is:

```
Number of links = (N(N − 1)) / 2
```

* Provides high reliability and fault tolerance due to multiple alternative paths.
* Expensive and complex to install and maintain because of a large number of links.

---

### Bus Topology

* All devices are connected to a single shared communication channel called the **backbone cable**.
* For **N** devices, one main cable is required and it is connected by drop lines with each individual device.
* Data transmitted by a device is broadcast to all devices on the network.
* Simple and cost-effective to implement.
* Less reliable and inefficient for large networks.

---

### Star Topology

* All devices are connected to a central device (**hub or switch**) using point-to-point cables.
* For **N** devices, **N** cables are required.
* Easy to install, manage, and troubleshoot.
* Failure of a single device does not affect the rest of the network.
* Failure of the central device can cause the entire network to stop working.

---

### Ring Topology

* Each device is connected to exactly two neighboring devices, forming a closed loop.
* Data travels in a circular direction (clockwise or counterclockwise).
* Provides orderly and controlled data transmission.
* Failure of a single device or link can disrupt the entire network.

*Read more about Network Topologies.*

---

## Transmission Modes

### Simplex Mode

* Communication is **unidirectional**, as on a one-way street.
* Only one of the two devices on a link can transmit, and the other can only receive.

### Half-Duplex Mode

* Each station can both transmit and receive, but **not at the same time**.

### Full-Duplex Mode

* Both stations can transmit and receive **simultaneously**.

*Read more about Transmission modes.*

---

## OSI Model

**OSI** stands for **Open Systems Interconnection**. It has been developed by **ISO – International Organization for Standardization**, in the year **1984**.

It is a **seven-layer architecture**, with each layer having specific functionality to perform.

**OSI-model-3.webp**

---

## Understanding Layers of OSI Model

### Physical Layer

The **Physical Layer** is the lowest layer of the OSI model and is responsible for the transmission of raw bits (**0s and 1s**) over a physical communication medium.

It defines the mechanical, electrical, and procedural characteristics required to establish and maintain physical connections between devices.

#### Key Responsibilities of the Physical Layer

* Bit transmission over the physical medium
* Defines voltage levels for binary data
* Specifies data rate (bits per second)
* Determines bit synchronization
* Defines line configuration (point-to-point or multipoint)
* Specifies physical topology
* Defines transmission modes (simplex, half duplex, full duplex)

---

## Transmission Media

Transmission media refer to the physical or wireless paths through which data travels from the sender to the receiver in a computer network.

They are mainly classified into:

* **Guided (Wired) Media**
* **Unguided (Wireless) Media**

---

### Guided Transmission Media (Wired)

Guided media use a physical path (cables) to transmit data signals.

#### Characteristics

* Data travels through solid conductors
* More secure and reliable
* Less interference and noise
* Limited mobility

#### Types

* **Twisted Pair Cable** – low cost, commonly used in LANs
* **Coaxial Cable** – better noise resistance, used in cable TV
* **Optical Fiber** – very high speed and bandwidth, long-distance communication

---

### Non-Guided Transmission Media (Wireless)

Non-guided media transmit data using electromagnetic waves without physical cables.

#### Characteristics

* No physical connection required
* Supports mobility and flexibility
* Easier and faster deployment
* More prone to interference and security risks

#### Types

* **Radio Waves** – Wi-Fi, Bluetooth
* **Microwaves** – cellular and satellite communication
* **Infrared** – short-range communication

# Switching Techniques

Switching techniques are methods used in a network to establish a path and transfer data from a source to a destination through intermediate nodes.

---

## Circuit Switching

In circuit switching, a **dedicated communication path** is established for the entire communication session.

**Phases:**

* Connection setup → data transfer → connection termination
* Fixed bandwidth throughout the communication

**Example:** Traditional telephone networks (PSTN)

**Advantages:**

* Predictable and continuous data flow

**Disadvantages:**

* Inefficient use of resources
* Path remains reserved even when idle

---

## Message Switching

In message switching, the **entire message** is sent to an intermediate node, stored, and then forwarded until it reaches the destination.

* No dedicated path required

**Example:** Email systems

**Advantages:**

* Efficient use of resources
* No need for a dedicated path

**Disadvantages:**

* High delays due to storing and forwarding large messages

---

## Packet Switching

In packet switching, data is divided into **small packets** that are routed independently to the destination.

* No dedicated path required
* Packets may follow different routes

**Example:** Internet (TCP/IP)

**Advantages:**

* Efficient bandwidth utilization
* Flexible and scalable

**Disadvantages:**

* Packet reordering possible
* Header overhead

---

## Comparison of Switching Techniques

| Feature               | Circuit Switching  | Packet Switching | Message Switching |
| --------------------- | ------------------ | ---------------- | ----------------- |
| Dedicated path        | Yes                | No               | No                |
| Data transmission     | Continuous stream  | Packets          | Complete message  |
| Delay                 | Low after setup    | Variable         | High              |
| Bandwidth utilization | Low                | High             | Low               |
| Usage                 | Telephone networks | Internet         | Telegraph systems |

---

# Data Link Layer

The **Data Link Layer** is the second layer of the OSI model. It ensures **node-to-node delivery** of data and reliable transmission of frames over a physical link.

---

## Functions of Data Link Layer

* **Framing** – divides raw bit stream into frames
* **Error control** – detects and corrects transmission errors
* **Flow control** – prevents sender from overwhelming receiver
* **Medium Access Control (MAC)** – controls access to shared medium
* **Physical addressing** – uses MAC addresses

---

## Basic Time Delays

### 1. Transmission Delay (Td)

Time taken to place all bits of a frame onto the transmission medium.

```
Td = Length of packet / Bandwidth
```

### 2. Propagation Delay (Pd)

Time taken by a signal to travel from sender to receiver.

```
Pd = Distance / Propagation speed
```

### 3. Round Trip Time (RTT)

Total time taken for a frame to reach the receiver and for its acknowledgment to return.

Also known as **minimum acknowledgment waiting time**.

---

## Flow Control Mechanisms

Flow control ensures that the sender does not transmit data faster than the receiver can handle.

---

### 1. Stop and Wait Protocol

* Only one frame is sent at a time
* Sender waits for ACK before sending the next frame
* Simple but inefficient

**Efficiency:**

```
E = Td(frame) / [Td(frame) + 2Pd + Qd + Prd + Td(ACK)]
```

**Throughput:**

```
Throughput = L / [Td(frame) + 2Pd + Qd + Prd + Td(ACK)]
```

---

### 2. Go-Back-N ARQ

* Conservative protocol
* Uses cumulative acknowledgments
* Receiver window size = 1
* Sender window size = 2^k − 1

**Efficiency:**

```
E = N × Td(frame) / [Td(frame) + 2Pd + Qd + Prd + Td(ACK)]
```

**Throughput:**

```
Throughput = N × L / [Td(frame) + 2Pd + Qd + Prd + Td(ACK)]
```

---

### 3. Selective Repeat ARQ

* Retransmits only lost or corrupted frames
* More efficient than Go-Back-N
* Requires higher buffer

**Efficiency:**

```
E = N × Td(frame) / [Td(frame) + 2Pd + Qd + Prd + Td(ACK)]
```

---

## Framing in Data Link Layer

Framing provides a way for a sender to transmit a set of bits that are meaningful to the receiver.

### Character / Byte Stuffing

* Used when frames consist of characters
* If data contains ED, an extra byte is stuffed

### Bit Stuffing

* Sender stuffs a bit to break the pattern

```
0111 1 → 0111 0 1
```

---

## Medium Access Control Protocols

MAC protocols manage how devices share a common communication medium.

---

### Contention-Based Protocols

* Devices compete for medium
* Collisions may occur

**Examples:**

#### ALOHA

* Pure ALOHA: Transmit anytime, collisions resolved by retransmission
* Slotted ALOHA: Time divided into slots

#### CSMA

* CSMA/CD: Ethernet
* CSMA/CA: Wireless (Wi‑Fi) using RTS/CTS

---

### Controlled Access Protocols

* Polling
* Token Passing

---

## Error Control

### Hamming Code

Error correction code for detecting and correcting errors.

**Redundant bits condition:**

```
2^r ≥ m + r + 1
```

Where:

* r = redundant bits
* m = data bits

### Cyclic Redundancy Check (CRC)

Uses polynomial generator at sender and receiver.

Example:

* Data: 1010000
* Polynomial: x^3 + 1

### Checksum

More reliable error detection using checksum generator and checker.

---

# Network Layer

The **Network Layer** handles logical addressing, routing, and packet forwarding across networks.

---

## Classful Addressing

Divides IP addresses into five classes: A, B, C, D, E.

Click to enlarge

---

## IPv4 Datagram Header

The IPv4 header contains routing and control information.

* VERSION: 4 bits (IPv4)
* HLEN: Header length (4 bits)
* Type of Service: Delay, Throughput, Reliability
* Total Length: 20 to 65,535 bytes
* Identification: Packet ID
* Flags: Reserved, DF, MF
* Fragment Offset
* Time to Live (TTL)
* Protocol
* Header Checksum
* Source IP Address
* Destination IP Address
* Options

---

## Subnetting

Subnetting divides a large network into smaller networks.

### Why Subnetting is Needed

* Reduces broadcast traffic
* Improves security
* Efficient IP utilization

### Example

Network: 192.168.1.0/24

* Required subnets: 4
* New prefix: /26
* Subnet mask: 255.255.255.192

**Subnets:**

* 192.168.1.0 – 192.168.1.63
* 192.168.1.64 – 192.168.1.127
* 192.168.1.128 – 192.168.1.191
* 192.168.1.192 – 192.168.1.255

Each subnet has 62 usable IPs.

---

## Supernetting

Combines multiple networks into one.

**Purpose:**

* Reduces routing table size
* Enables route summarization

---

## VLSM

Allows different subnet masks in the same network.

**Advantages:**

* Efficient IP usage
* Flexible design

---

## ICMP

Used for error reporting and diagnostics.

**Common Messages:**

* Destination Unreachable
* Time Exceeded
* Echo Request / Reply

---

## Routing Protocols Comparison

| DVR              | LSR         |
| ---------------- | ----------- |
| Bellman-Ford     | Dijkstra    |
| Periodic updates | Event-based |
| Slow             | Fast        |
| RIP              | OSPF        |

---

## OSPF

Link-state routing protocol using Dijkstra’s algorithm.

---

## RIP

Distance vector routing protocol using hop count.

* Max hops: 15
* AD: 120
* Port: 520

---

## ARP and RARP

* **ARP** maps IP to MAC
* **RARP** maps MAC to IP

---

# Transport Layer

Responsible for end-to-end communication and reliability.

---

## TCP

Reliable, connection-oriented protocol.

### TCP Congestion Control

* Slow Start
* Congestion Avoidance
* Congestion Detection

### TCP 3-Way Handshake

1. SYN
2. SYN + ACK
3. ACK

### TCP Termination

* Graceful release
* Abrupt release

---

## UDP

Connectionless, fast but unreliable.

---

## TCP vs UDP

| TCP             | UDP          |
| --------------- | ------------ |
| Reliable        | Unreliable   |
| 3-way handshake | No handshake |
| Slower          | Faster       |
| 20 bytes        | 8 bytes      |

---

# Session Layer

Manages sessions between devices.

Functions:

* Session establishment
* Maintenance
* Termination
* Synchronization
* Session identification

---

# Presentation Layer

Handles data translation, encryption, and compression.

---

# Application Layer

Provides services to end-user applications.

Functions:

* Resource access
* Email services
* File transfer
* Name resolution
* Client-server communication

---
# TCP/IP Model

The **TCP/IP model** is a practical and implementation-oriented networking model used in real-world networks, including the Internet. It was developed by **DARPA (Defense Advanced Research Projects Agency)** and forms the foundation of modern data communication.

Unlike the **OSI model** (7 layers), the TCP/IP model consists of **4 layers**, each responsible for a specific set of networking functions.

---

## Layers of TCP/IP Model

1. Application Layer
2. Transport Layer
3. Internet Layer
4. Network Access Layer

---

## Application Layer in TCP/IP Model

The **Application Layer** is the topmost layer of the TCP/IP model. It provides network services directly to user applications and enables communication between software applications over a network.

### OSI Layers Combined

In the TCP/IP model, this layer combines the responsibilities of:

* Application Layer (OSI Layer 7)
* Presentation Layer (OSI Layer 6)
* Session Layer (OSI Layer 5)

---

### Key Functions of Application Layer

#### User-Level Network Services

* Enables applications to access network resources
* Supports web browsing, email, file transfer, and remote login

#### Data Representation and Formatting

Handles:

* Data translation
* Character encoding
* Data compression
* Encryption and decryption

#### Session Management

* Establishes, maintains, and terminates communication sessions
* Supports synchronization and dialog control

#### Name Resolution

* Converts domain names into IP addresses
* Makes network usage human-friendly

#### Application Communication

* Enables client–server interaction
* Supports request–response and message-based communication

---

### Features of Application Layer (TCP/IP)

* Closest layer to the user
* Protocol-oriented
* Platform-independent
* Supports multiple application services
* Does not handle packet delivery or routing

---

## Transport Layer in TCP/IP Model

The **Transport Layer** is the second layer of the TCP/IP model. It is responsible for **end-to-end (process-to-process) communication** between applications running on different hosts.

It ensures that data sent from a source application is delivered to the correct destination application reliably or efficiently, depending on the protocol used.

---

### Key Functions of the Transport Layer

#### Process-to-Process Communication

* Uses port numbers to identify source and destination applications
* Enables multiple applications to communicate simultaneously on the same host

#### Segmentation and Reassembly

* Breaks large data into smaller units called segments
* Reassembles segments at the receiver side

#### Multiplexing and Demultiplexing

* **Multiplexing:** Multiple applications send data using a single network connection
* **Demultiplexing:** Data is delivered to the correct application using port numbers

#### Flow Control

* Ensures the sender does not exceed the receiver’s processing capacity
* Uses sliding window mechanism (TCP)

#### Error Control

* Detects errors using checksums
* Retransmits lost or corrupted data (TCP)

#### Congestion Control

* Adjusts data transmission rate based on network congestion
* Prevents network overload

---

## Internet Layer in TCP/IP Model

The **Internet Layer** is the third layer of the TCP/IP model. It is responsible for **logical addressing, packet routing, and delivery of data across interconnected networks**.

It determines how packets move from the source host to the destination host, even if both are on different networks.

---

### Key Functions of Internet Layer

#### Logical Addressing

* Assigns IP addresses to devices
* Ensures unique identification of hosts across networks
* Supports IPv4 (32-bit) and IPv6 (128-bit)

#### Packet Routing

* Determines the best path from source to destination
* Uses routing algorithms and routing tables

#### Packet Forwarding

* Moves packets from one router to the next
* Uses next-hop routing

#### Fragmentation and Reassembly

* Breaks large packets to match MTU size
* Reassembles fragments at destination host

#### Error Reporting and Diagnostics

* Reports network-level errors:

  * Destination unreachable
  * Time exceeded
* Helps in troubleshooting

---

## Network Access Layer in TCP/IP Model

The **Network Access Layer** is the lowest layer of the TCP/IP model. It is responsible for physical transmission of data over the network medium.

It combines the functionalities of:

* Data Link Layer (OSI Layer 2)
* Physical Layer (OSI Layer 1)

---

### Key Functions of Network Access Layer

#### Framing

* Encapsulates IP packets into frames
* Adds:

  * Source MAC address
  * Destination MAC address
  * Error detection information

#### Physical Addressing (MAC Addressing)

* Uses 48-bit MAC addresses
* Ensures correct delivery within a LAN

#### Media Access Control

* Controls how devices share the medium
* Prevents or manages collisions

**Examples:**

* CSMA/CD (Ethernet)
* CSMA/CA (Wi-Fi)

#### Error Detection

* Detects errors using:

  * CRC (Cyclic Redundancy Check)
* Error correction is not performed

#### Bit Transmission

* Converts frames into binary signals
* Defines:

  * Voltage levels
  * Data rate
  * Transmission mode

---

## Difference Between OSI Model and TCP/IP Model

| OSI Model                    | TCP/IP Model                                      |
| ---------------------------- | ------------------------------------------------- |
| Open Systems Interconnection | Transmission Control Protocol / Internet Protocol |
| Developed by ISO             | Developed by DARPA                                |
| 7 layers                     | 4 layers                                          |
| Conceptual model             | Practical model                                   |
| Strict architecture          | Flexible architecture                             |
| Protocol-independent         | Protocol-oriented                                 |
| Educational use              | Real-world use                                    |
| Rarely implemented fully     | Widely implemented                                |

---

## Common Network Protocols: Ports, Layers, and Functions

| Protocol (Port) | Layer          | Function                 |
| --------------- | -------------- | ------------------------ |
| HTTP (80)       | Application    | Web page transfer        |
| HTTPS (443)     | Application    | Secure web communication |
| FTP (21/20)     | Application    | File transfer            |
| SMTP (25)       | Application    | Email sending            |
| IMAP (143)      | Application    | Email access             |
| DNS (53)        | Application    | Name resolution          |
| Telnet (23)     | Application    | Remote login             |
| SSH (22)        | Application    | Secure remote access     |
| SNMP (161/162)  | Application    | Network management       |
| DHCP (67/68)    | Application    | Automatic IP assignment  |
| TCP             | Transport      | Reliable delivery        |
| UDP             | Transport      | Fast delivery            |
| IP              | Internet       | Routing and addressing   |
| ICMP            | Internet       | Error reporting          |
| ARP             | Internet       | IP to MAC mapping        |
| Ethernet        | Network Access | Framing & MAC            |
| Wi-Fi           | Network Access | Wireless LAN             |

---

## Network Devices

**Network Devices** are hardware components used to connect, manage, control, and communicate data between computers and other devices within a network.

They enable:

* Data transmission
* Routing
* Network security
* Network management
