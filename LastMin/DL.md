# Digital Electronics

Digital electronics deals with systems that use digital signals (0s and 1s) to process information. It is the backbone of modern devices such as computers, smartphones, and calculators. Unlike analog electronics, which works with continuous signals, digital electronics offers higher accuracy, reliability, and noise resistance.

## Logic Gates

Logic gates are the basic building blocks of digital circuits. They perform logical operations on one or more binary inputs to produce a single binary output.

### Types of Logic Gates
AND Gate (·), OR Gate (+), NOT Gate (′), XOR Gate, NAND Gate, NOR Gate, XNOR Gate, Buffer Gate, Universal Logic Gates

### AND Gate (·)
Output is 1 only when all inputs are 1.  
Y = A · B

### OR Gate (+)
Output is 1 if any input is 1.  
Y = A + B

### NOT Gate (′)
Output is the inverse of input.  
Y = A′

### XOR Gate
Output is 1 if inputs are different.  
Y = A ⊕ B

### NAND Gate
Output is 0 only when all inputs are 1.  
Y = (A · B)′

### NOR Gate
Output is 1 only when all inputs are 0.  
Y = (A + B)′

### XNOR Gate
Output is 1 when inputs are same.  
Y = (A ⊕ B)′

### Buffer Gate
Output equals input.  
Y = A

### Universal Logic Gates
NAND and NOR are universal gates; any digital circuit can be built using only these.

## Minimization of Boolean Functions

Minimization reduces the number of terms, literals, and gates without changing functionality.

### Algebraic Simplification
F(A,B) = AB + A  
F(A,B) = A

### Karnaugh Map (K-Map)
A visual method to simplify Boolean expressions by grouping adjacent 1s.

## Representation of Boolean Functions

### Sum of Products (SOP)
Y = AB + BC  
f(A,B,C) = Σm(3,5,6,7)

### Product of Sums (POS)
Y = (A + B + C)(A + B + C′)  
f(A,B,C) = πM(0,1,2,4)

## Don’t Care Conditions
Unused outputs treated as X for simplification.

Example:  
f = m(1,5,6,11,12,13,14) + d(4)  
Minimal SOP:  
f = BC′ + BD′ + A′C′D + AB′CD

## Boolean Algebra Laws

### De Morgan’s Laws
(A · B)′ = A′ + B′  
(A + B)′ = A′ · B′

### Absorption Law
A + AB = A  
A(A + B) = A

### Domination Law
A + 1 = 1  
A · 0 = 0

### Consensus Law
AB + A′C + BC = AB + A′C

## Duality Theorem
Swap AND with OR and 0 with 1.

Example:  
A + (BC) ↔ A · (B + C)

## Combinational Circuits
Output depends only on current inputs.

### Adders

Half Adder:  
S = A ⊕ B  
C = A · B

Full Adder:  
S = A ⊕ B ⊕ Cin  
Cout = AB + BCin + ACin

### Subtractors

Half Subtractor:  
D = A ⊕ B  
Borrow = A′ · B

Full Subtractor:  
D = A ⊕ B ⊕ Bin  
Borrow = A′(B ⊕ Bin) + (B · Bin)

### Multiplexer (MUX)
Selects one input from many using select lines.

### Demultiplexer (DEMUX)
Routes one input to multiple outputs.

### Encoder
Converts 2ⁿ inputs into n-bit output.  
Priority Encoder gives priority to highest input.

### Decoder
Converts n-bit input to 2ⁿ outputs.

### Comparator
Compares two numbers. Outputs: A>B, A=B, A<B.

## Sequential Circuits
Output depends on current input and previous state.

Types:  
Asynchronous, Synchronous

## Flip-Flops
Basic memory elements storing 1 bit.

### SR Flip-Flop
Uses Set and Reset inputs.

### JK Flip-Flop
Eliminates invalid SR condition.

### D Flip-Flop
Q = D

### T Flip-Flop
Toggles output on each clock.

## Number System

A number system represents numbers using a base (radix).

Types:  
Decimal (10), Binary (2), Octal (8), Hexadecimal (16)

## Number System Conversions

Decimal to Binary:  
(10.25)₁₀ = (1010.01)₂

Binary to Decimal:  
(1010.01)₂ = (10.25)₁₀

Decimal to Octal:  
(10.25)₁₀ = (12.2)₈

Octal to Decimal:  
(12.2)₈ = (10.25)₁₀

Hexadecimal to Binary:  
(3A)₁₆ = (00111010)₂

Binary to Hexadecimal:  
(001111011011)₂ = (3DB)₁₆

Binary to Octal:  
(111101101)₂ = (755)₈
