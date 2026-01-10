# C Programming Last Minute Notes

C programming is a powerful and widely-used programming language that forms the backbone of many modern technologies. Known for its simplicity and efficiency, it is the foundation for learning advanced programming concepts. This "Last Minute Notes" article is designed to provide a quick and concise revision of the key topics in C programming, including data types, operators, control flow statements, functions, and storage classes.

## Table of Content
- Data Types and Operators
- Control Flow Statements
- Storage Class & Function

---

## Data Types and Operators

### Data Types

#### 1. Primitive Data Type

**(a) Integer Types:**
- short int, unsigned short int
- int, unsigned int
- long int, unsigned long int
- long long int, unsigned long long int

**(b) Character Types:**
- char, unsigned char

**(c) Floating Types:**
- float, double, long double

**(d) Other:**
- void, bool

#### 2. Non-Primitive Data Type

**(a) Derived Data Type:**
- Array
- Pointer
- String

**(b) User-defined Data Type:**
- Structure
- Union
- Enum
- Typedef

**Note:**
- C standard does not specify how many bits/bytes to allocate for every type. Compilers may choose different ranges.
- Short and int types are at least 16 bits, long types are at least 32 bits.  
[Read more about - Data Types](#)

---

## Operators

### 1. Arithmetic Operators
Used for mathematical calculations:

- `+` (Addition): Adds two operands. Example: `a + b`
- `-` (Subtraction): Subtracts second operand from the first. Example: `a - b`
- `*` (Multiplication): Multiplies two operands. Example: `a * b`
- `/` (Division): Divides first operand by the second. Example: `a / b`
- `%` (Modulus): Gives the remainder of division (works with integers only). Example: `a % b`

### 2. Relational Operators
Used to compare two values, returning true (`1`) or false (`0`):

- `<` (Less than)
- `>` (Greater than)
- `<=` (Less than or equal to)
- `>=` (Greater than or equal to)
- `==` (Equal to)
- `!=` (Not equal to)

### 3. Logical Operators
Used for logical conditions, returning true (`1`) or false (`0`):

- `&&` (Logical AND): Returns true if both conditions are true. Example: `a > 0 && b > 0`
- `||` (Logical OR): Returns true if at least one condition is true. Example: `a > 0 || b > 0`
- `!` (Logical NOT): Inverts the boolean value. Example: `!(a > b)`

### 4. Assignment Operator
Used to assign values:

- `=`  
Example: `int a = 5;`

### 5. Increment and Decrement Operators
Used to increase or decrease a value by 1:

- `++x` (Pre-increment): Increments the value of x before using it.
- `x++` (Post-increment): Uses the current value of x and then increments it.
- `--x` (Pre-decrement): Decrements the value of x before using it.
- `x--` (Post-decrement): Uses the current value of x and then decrements it.

Example:  
```c
int x = 5;
printf("%d", ++x); // Outputs 6

```
### 6. Bitwise Operators
Operate at the bit level:

- `&` (AND): Sets each bit to 1 if both bits are 1.
- `|` (OR): Sets each bit to 1 if at least one bit is 1.
- `^` (XOR): Sets each bit to 1 if the bits are different.
- `~` (NOT): Inverts all the bits.
- `<<` (Left Shift): Shifts bits to the left, adding 0s on the right.
- `>>` (Right Shift): Shifts bits to the right, removing bits on the right.

**Example:**  
```c
int a = 5; // Binary: 0101
int b = a << 1; // Result: 1010 (Decimal 10)
```
### 7. Ternary Operator
A shorthand for if-else:

**Syntax:**  
`condition ? value_if_true : value_if_false`

**Example:**  
```c
int a = 10, b = 5;
int max = (a > b) ? a : b; // Assigns the larger value to max
```
# Control Flow Statements

---

## A) Decision-Making Statements

### 1. If Statement
Executes a block of code if a condition is true.

**Syntax:**
```c
if (condition) {   
  // statements to execute if condition is true 
}
```

### 2. If-Else Statement
Executes one block if the condition is true; another block if false.

**Syntax:**
```c
if (condition) {   
  // statements if condition is true 
} else {    
  // statements if condition is false 
}
```

### 3. Else-If Ladder
Used when multiple conditions need to be tested.

**Syntax:**
```c
if (condition1) { 
    // statements
} else if (condition2) {
    // statements 
} else { 
    // default statements
}
```

### 4. Switch Statement
Selects one of many blocks of code to execute based on a specific value.

**Syntax:**
```c
switch (expression) {
    case value1: 
        // statements
        break;
    case value2: 
        // statements
        break;
    default: 
        // default statements 
}
```

---

## B) Looping Statements

### 1. For Loop
The for statement evaluates 3 expressions and executes the loop body until second controlling expression executes to false. Recommended when the number of iterations is known in advance.

**Syntax:**
```c
for (initialization; condition; increment/decrement) { 
    // statements 
}
```

- **expression – 1**: evaluated once before the first iteration of the loop.  
- **expression – 2**: determines whether to terminate the loop, evaluated before every iteration. If true (non-zero), loop executes; if false (zero), loop terminates.  
- **expression – 3**: evaluated after each iteration.  

### 2. While Loop
The while statement evaluates a controlling expression before every execution of the loop body.

**Syntax:**
```c
while (condition) { 
    // statements 
}
```

### 3. Do-While Loop
Both for and while loops check the loop termination condition before every iteration, but do-while checks after executing the loop body. Executes at least once.

**Syntax:**
```c
do {
    // statements 
} while (condition);
```

---

## C) Jump Statements

### 1. Break Statement
Exits the nearest enclosing loop or switch statement.

**Example:**
```c
for (int i = 1; i <= 5; i++) {
    if (i == 3) break;
    printf("%d
", i); 
}
```

### 2. Continue Statement
Skips the rest of the current loop iteration and moves to the next iteration.

**Example:**
```c
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    printf("%d
", i);
}
```

### 3. Goto Statement
Transfers control to a labeled statement.

**Example:**
```c
int i = 1;
start:
if (i <= 5) {
    printf("%d
", i);
    i++; 
    goto start;
}
```

Read more about - Control Flow Statements

---

# Storage Class & Function

## 1. Memory Organization of a C Program
A C program's memory is divided into several segments:

### Code Segment
- Contains executable instructions of the program.  
- Typically read-only and sharable.  

### Data Segment
- **Initialized Data Segment**: Stores global/static variables initialized by the programmer.  
- **Uninitialized Data Segment (BSS)**: Stores uninitialized global/static variables; initialized to zero by default.  

### Stack
- Stores local variables and function call information.  
- Follows the Last In, First Out (LIFO) principle.  

### Heap
- Used for dynamic memory allocation during runtime (e.g., using malloc() or calloc()).  

---

## 2. Storage Classes in C
Storage classes determine the characteristics of a variable such as scope, lifetime, and default value.

---

## 3. Functions in C

### Function Declaration
Functions are blocks of code designed to perform specific tasks. They improve modularity and reusability.

**Syntax:**
```c
return_type function_name(parameters);
```

### Function Definition
```c
return_type function_name(parameters) {     
    // function body 
}
```

---

## 4. Recursion
A function that calls itself either directly or indirectly. Requires a base condition to prevent infinite recursion.

**Example (Factorial):**
```c
int factorial(int n) {
    if (n == 0) return 1; // Base condition
    return n * factorial(n - 1); // Recursive call
}
```

---

## 5. Static and Dynamic Scoping

### Static Scoping
Variable binding is determined at compile-time. The scope of the variable depends on its declaration.

**Example:**
```c
int a = 10;
void main() {
    {
        int a = 1;
        {
            int b;
            printf("%d", a);
        }
    }
}
```

### Dynamic Scoping
Variable binding is determined at runtime. Scope is based on the call stack of the program.

**Example:**
```c
int i;
program main() {
    i = 10;
    call f();
}
procedure f() {
    int c = 20;
    call g();
}
procedure g() {
    print i;
}
```
