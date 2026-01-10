# Compiler Design

Compiler design is the study of how to build a compiler, which is a program that translates high-level programming languages (like Python, C++, or Java) into machine code that a computer's hardware can execute directly. The focus is on how the translation happens, ensuring correctness and making the code efficient.

* Helps understand how programming languages work internally.
* Essential for building compilers, interpreters, IDEs, and language tools.
* Improves knowledge of program analysis and optimisation.

## Phases of a Compiler

1. **Lexical Analysis**: Tokenisation of source code into meaningful units (tokens).
2. **Syntax Analysis**: Construction of a parse tree based on grammar rules.
3. **Semantic Analysis**: Ensures correctness of meaning (e.g., type checking).
4. **Intermediate Code Generation**: Produces an intermediate representation (IR) for optimisation and portability.
5. **Code Optimisation**: Enhances the efficiency of the intermediate code.
6. **Code Generation**: Translates optimised IR into target machine code.

*Read more about Phases of Compiler, Here.*

## Linking and Loading

### Linking

* Combining multiple object files into a single executable.
* Resolves symbolic references such as function calls and global variables.
* Performed by a linker after compilation.

**Example:** Linking connects a function call in one file to its actual definition in another file.

### Loading

* Placing the executable into main memory.
* Assigns actual memory addresses and prepares the program for execution.
* Performed by a loader before the CPU starts execution.

*Read more about Difference Between Linker and Loader, Here.*

## Lexical Analysis

Lexical analysis is the first phase of a compiler. It breaks the source code into small meaningful units called tokens.

### Key Functions

* **Tokenization:** Converts source code into tokens (keywords, identifiers, operators, literals). Example: `int a = 5;` → Tokens: `int, a, =, 5, ;`
* **Removing Whitespaces and Comments:** Ignored during token generation.
* **Error Detection:** Identifies errors like invalid symbols or unknown characters.

### Components

* **Lexical Analyzer (Lexer):** Performs tokenization.
* **Symbol Table:** Stores information about variables, functions, and other identifiers.
* **Output:** Sequence of tokens sent to Syntax Analysis.

### Token Categories

* **Keywords:** Reserved words (e.g., `int, if, while, return`).
* **Identifiers:** Names of variables, functions, arrays (e.g., `x, count, _value`).
* **Literals (Constants):** Fixed values (e.g., `10, 3.14, 'a', "hello"`).
* **Operators:** Symbols for operations (e.g., `+, -, *, ==, &&`).
* **Punctuation (Delimiters):** Symbols structuring the program (e.g., `;, ,, (), {}`).
* **Special Symbols:** Special-purpose symbols (e.g., `#, $`).

*Read more about Introduction of Lexical Analysis, Here.*

## Syntax Analysis and Parsing

Syntax analysis is the second phase of a compiler. It checks whether tokens from lexical analysis follow grammar rules.

### Key Functions

* **Parse Tree Construction:** Converts tokens into a hierarchical structure representing program syntax.
* **Grammar Validation:** Ensures code adheres to grammar rules.
* **Error Detection:** Identifies syntax errors (e.g., missing semicolons, unmatched parentheses).
* **Input:** Sequence of tokens from lexer.
* **Output:** Parse tree or syntax errors.

### Types of Grammar Used

* **Context-Free Grammar (CFG):** Defines syntax rules.
* **Production Rules:** Example: `E → E + T | T`.

*Read more about Context Free Grammar, Here.*

### Classification of CFG

* **Ambiguous Grammar:** A string has more than one parse tree.
* **Unambiguous Grammar:** Every string has exactly one parse tree.

### Syntax Tree vs Parse Tree

| Feature  | Parse Tree                      | Syntax Tree                                    |
| -------- | ------------------------------- | ---------------------------------------------- |
| Purpose  | Shows full derivation           | Shows semantic structure                       |
| Includes | All non-terminals and terminals | Only essential elements                        |
| Use      | Helps in syntactic analysis     | Helps in semantic analysis and code generation |

### Parser

A parser performs syntax analysis and outputs a parse tree or syntax errors.

### Classification of Parsers

#### Top-Down Parsers

* Build parse tree from root to leaves.
* Parse input left to right.
* Use leftmost derivation.
* Types:

  * Recursive Descent Parser
  * LL Parser (e.g., LL(1))

#### Bottom-Up Parsers

* Build parse tree from leaves to root.
* Parse input left to right.
* Use rightmost derivation in reverse.
* Types:

  * Operator Precedence Parser
  * LR Parser (LR(0), SLR, CLR, LALR)

*Read more about Types of Parsers, Here.*

## LL(1) Parser

* Reads input left to right.
* Constructs leftmost derivation.
* Uses 1 lookahead token.

### Grammar Conditions

* For grammar `A → α | β`:

  * `First(α) ∩ First(β) = ∅`
  * If `ε ∈ First(β)`, then `Follow(A) ∩ First(α) = ∅`

### Steps to Construct LL(1) Parsing Table

1. Remove left recursion.
2. Left factoring.
3. Find First and Follow sets.
4. Construct parsing table.

### Example Grammar

```
E → TE'
E' → +TE' | ε
T → FT'
T' → *FT' | ε
F → id | (E)
```

### First and Follow Sets

| Non-terminal | First   | Follow         |
| ------------ | ------- | -------------- |
| E            | {id, (} | { $, ) }       |
| E'           | {+, ε}  | { $, ) }       |
| T            | {id, (} | { +, $, ) }    |
| T'           | {*, ε}  | { +, $, ) }    |
| F            | {id, (} | { *, +, $, ) } |

### LL(1) Parsing Table

```
      id     +     *     (     )     $
E   E→TE'           E→TE'        
E'        E'→+TE'          E'→ε  E'→ε
T   T→FT'           T→FT'        
T'        T'→ε  T'→*FT'  T'→ε  T'→ε
F   F→id           F→(E)        
```

## Recursive Descent Parser

* Top-Down parser using recursive functions.
* Left-to-right parsing.
* Constructs leftmost derivation.
* Backtracking for mismatch.

*Read more about Recursive Descent Parser, Here.*

## Bottom-Up Parser

* Parse tree built from leaves to root.
* Operator Precedence Parser used for operator grammars.

### Operator Precedence Relations

| Symbol | Meaning                        |
| ------ | ------------------------------ |
| a ⋗ b  | a has higher precedence than b |
| a ⋖ b  | a has lower precedence than b  |
| a ≐ b  | a and b have equal precedence  |

### Bottom-Up Parsing Actions

* **Shift:** Move input symbol onto stack.
* **Reduce:** Replace stack symbols with LHS non-terminal.
* **Accept:** Parsing successful.

### Types of LR Parsers

* LR(0)
* SLR
* CLR
* LALR

### Steps for LR Parsing Table Construction

1. Augment grammar `S' → S`.
2. Construct canonical LR(0) items.
3. Compute Action and Goto tables.
4. Conflict checking.

*Read more about LR Parser, Here.*

## Syntax Directed Translation (SDT)

* Combines CFG with semantic rules.

### Attributes

* **Inherited:** From parent/sibling nodes.
* **Synthesized:** From child nodes.

### Syntax Directed Definitions (SDD)

* **L-Attributed Grammar:** Synthesized or restricted inherited attributes.
* **S-Attributed Grammar:** Only synthesized attributes.

### Examples

**Inherited:**

```
D → T L {L.in = T.type}
T → int {T.type = int}
L → id {AddType(id.entry, L.in)}
```

**Synthesized:**

```
E → E1 + T {E.val = E1.val + T.val}
T → int {T.val = int}
```

## Intermediate Code Generation and Optimization

### Three-Address Code (3AC)

* Each statement has at most 3 operands.
* Example:

```
u = t - z
v = u * w
w = v + t
```

### Static Single Assignment (SSA) Code

* Each variable assigned exactly once.
* Simplifies optimization.
* Example:

```
x = u - t
y = x * v
p = y + w
q = t - x
r = p * q
```

### Control Flow Graph (CFG)

* Nodes: basic blocks.
* Edges: control flow.
* Identify leaders and form blocks.
* Applications: detect independent code blocks, enable optimizations.

### Code Optimization Techniques

1. **Constant Folding**: `x = 2 * 3 + y → x = 6 + y`
2. **Copy Propagation**: `z = y + 2 → z = x + 2` if `x=y`
3. **Strength Reduction**: `x = 2 * y → x = y + y`
4. **Dead Code Elimination**: Remove unused code.
5. **Common Subexpression Elimination**:

```
x = (a+b)+(a+b)+c → t1 = a+b → x = t1 + t1 + c
```

6. **Loop Optimization:** code motion, induction variable elimination, loop jamming, loop unrolling.
7. **Peephole Optimization:** analyze short instruction sequences and replace with faster alternatives.
