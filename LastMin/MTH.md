# Linear Algebra

## Matrices

A **matrix** is a rectangular array of numbers arranged in **rows** and **columns**.

* **Order**: Denoted as ( m \times n ), where ( m ) is the number of rows and ( n ) is the number of columns.

### Example of Matrix

A matrix ([M]) has **3 rows and 2 columns**, i.e., order ( 3 \times 2 ).
Each element of matrix ([M]) can be referred to by its row and column number.

Example: ( a_{32} = 0 ).

---

## Types of Matrices

* **Square Matrix**: ( m = n )
* **Diagonal Matrix**: All non-diagonal elements are zero
* **Identity Matrix (I)**: Diagonal matrix with all diagonal elements equal to 1
* **Zero Matrix**: All elements are zero
* **Symmetric Matrix**: ( A = A^T )
* **Skew-Symmetric Matrix**: ( A = -A^T )
* **Orthogonal Matrix**: ( A^T A = I )
* **Singular Matrix**: ( |A| = 0 )
* **Non-Singular Matrix**: ( |A| \neq 0 )
* **Idempotent Matrix**: ( A^2 = A )
* **Involutory Matrix**: ( A^2 = I )
* **Nilpotent Matrix**: ( A^k = 0, ; k \le n )

---

## Operations on Matrices

* Matrix Addition
* Matrix Multiplication
* Transpose of a Matrix
* Inverse of a Matrix

### Transpose of a Matrix

The transpose ( A^T ) of an ( m \times n ) matrix ( A = [a_{ij}] ) is an ( n \times m ) matrix:

[
(A^T)*{ij} = a*{ji}
]

#### Properties of Transpose

* ( (A^T)^T = A )
* ( (kA)^T = kA^T )
* ( (A \pm B)^T = A^T \pm B^T )
* ( (AB)^T = B^T A^T )
* ( (A^{-1})^T = (A^T)^{-1} )

---

## Adjoint of a Matrix

The **adjoint** of a square matrix is the transpose of its **cofactor matrix**.

### Properties of Adjoint

* ( A(\text{Adj }A) = (\text{Adj }A)A = |A|I_n )
* ( \text{Adj}(AB) = (\text{Adj }B)(\text{Adj }A) )
* ( |\text{Adj }A| = |A|^{n-1} )
* ( \text{Adj}(\text{Adj }A) = |A|^{n-2} A )
* ( \text{Adj}(A^T) = (\text{Adj }A)^T )
* ( \text{Adj}(kA) = k^{n-1}\text{Adj }A )

---

## Inverse of a Matrix

For any square matrix ( A ):

[
A^{-1} = \frac{\text{Adj }A}{|A|}, \quad |A| \neq 0
]

### Properties of Inverse

* ( A^{-1}A = I )
* ( (A^{-1})^{-1} = A )
* ( (AB)^{-1} = B^{-1}A^{-1} )
* ( (kA)^{-1} = \frac{1}{k}A^{-1} )

> **Note**: Only a non-singular square matrix has an inverse.

---

## Conjugate of a Matrix

If ( A = [a_{ij}] ), then the conjugate matrix ( \overline{A} ) is obtained by taking the complex conjugate of each element:

[
\overline{A} = [\overline{a_{ij}}]
]

---

## Trace of a Matrix

For a square matrix ( A = [a_{ij}]_{n\times n} ):

[
\text{tr}(A) = a_{11} + a_{22} + \cdots + a_{nn}
]

* Trace equals the **sum of eigenvalues**.

### Properties of Trace

* ( \text{tr}(kA) = k\text{tr}(A) )
* ( \text{tr}(A+B) = \text{tr}(A) + \text{tr}(B) )
* ( \text{tr}(A-B) = \text{tr}(A) - \text{tr}(B) )
* ( \text{tr}(AB) = \text{tr}(BA) )

---

## Determinant of Matrices

The **determinant** represents the scaling factor of the linear transformation.

### Properties of Determinant

* ( |A^T| = |A| )
* ( |AB| = |A||B| )
* ( |kA| = k^n |A| )
* ( |A| = 0 \Rightarrow A \text{ is singular} )
* Interchanging rows/columns changes the sign of determinant

---

## Rank of a Matrix

The **rank** of a matrix is:

* Number of non-zero rows in row-reduced form
* Maximum number of linearly independent rows or columns

Denoted as ( \rho(A) ).

### Properties of Rank

* Null matrix: ( \rho(A) = 0 )
* Identity matrix ( I_n ): ( \rho(A) = n )
* ( \rho(A_{m\times n}) \le \min(m,n) )
* If ( |A| \neq 0 ), then ( \rho(A) = n )
* ( \rho(AB) \le \min(\rho(A), \rho(B)) )
* ( \rho(AB) \ge \rho(A) + \rho(B) - n )
* Rank of skew-symmetric matrix ( \neq 1 )

---

## System of Linear Equations

### Types of Solutions

* No Solution
* Unique Solution
* Infinite Solutions

### Homogeneous System ( AX = 0 )

* Trivial solution: ( X = 0 )
* If ( \rho(A) = ) number of unknowns → unique solution
* If ( \rho(A) < ) number of unknowns → infinite solutions

### Non-Homogeneous System ( AX = B )

* ( \rho[A:B] \neq \rho(A) ) → no solution
* ( \rho[A:B] = \rho(A) = ) number of unknowns → unique solution
* ( \rho[A:B] = \rho(A) \neq ) number of unknowns → infinite solutions

---

## Linear Dependence and Independence

### Linear Dependence

[
k_1X_1 + k_2X_2 + \cdots + k_rX_r = 0
]
for some scalars not all zero.

### Linear Independence

Only possible when:
[
k_1 = k_2 = \cdots = k_r = 0
]

### Determination

* Rank < number of vectors → dependent
* Rank = number of vectors → independent

---

## Eigen Values and Eigen Vectors

[
AX = \lambda X
]

### Characteristic Equation

[
|A - \lambda I| = 0
]

### Properties of Eigen Values

* Real symmetric / Hermitian → real eigenvalues
* Skew symmetric → imaginary or zero
* Orthogonal / unitary → (|\lambda| = 1)
* Sum of eigenvalues = trace of matrix
* Product of eigenvalues = determinant

---

## LU Decomposition

[
A = LU
]

* ( L ): Lower triangular matrix with 1s on diagonal
* ( U ): Upper triangular matrix

---

# Probability and Statistics

## Probability

Probability measures the likelihood of events.

### Basic Terminologies

* Sample Space (S)
* Event (E)
* ( 0 \le P(E) \le 1 )
* ( P(S) = 1 )
* ( P(\emptyset) = 0 )

### Important Rules

**Addition Rule**:

* ( P(A \cup B) = P(A) + P(B) ) (Mutually exclusive)
* ( P(A \cup B) = P(A) + P(B) - P(A \cap B) )

**Multiplication Rule**:

* ( P(A \cap B) = P(A)P(B) )
* ( P(A|B) = \frac{P(A \cap B)}{P(B)} )

---

## Random Variables

* Discrete Random Variable
* Continuous Random Variable

### Probability Distributions

**PMF**:
[
\sum f(x) = 1
]

**PDF**:
[
\int_{-\infty}^{\infty} f(x)dx = 1
]

### Expectation and Variance

* ( E[X] )
* ( Var(X) = E[X^2] - (E[X])^2 )

---

## Important Distributions

### Binomial Distribution

[
P(X=k) = \binom{n}{k}p^k(1-p)^{n-k}
]

Mean = ( np ), Variance = ( np(1-p) )

### Poisson Distribution

[
P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}
]

Mean = Variance = ( \lambda )

### Normal Distribution

[
f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}
]

---

# Calculus

## Limits

[
\lim_{x\to a^-}f(x) = \lim_{x\to a^+}f(x)
]

### L'Hospital Rule

[
\lim_{x\to a} \frac{f(x)}{g(x)} = \lim_{x\to a} \frac{f'(x)}{g'(x)}
]

---

## Continuity

[
\lim_{x\to x_0} f(x) = f(x_0)
]

---

## Differentiability

[
f'(x) = \lim_{h\to 0} \frac{f(x+h)-f(x)}{h}
]

---

## Mean Value Theorems

### Lagrange's MVT

[
f'(c) = \frac{f(b)-f(a)}{b-a}
]

### Rolle's Theorem

[
f'(c) = 0
]

---

## Integration

### Indefinite Integrals

[
\int f(x)dx = F(x) + C
]

### Definite Integrals

[
\int_a^b f(x)dx = F(b) - F(a)
]

---

## Applications of Integrals

* Area under curve
* Area between curves
* Arc length
* Volume and surface area of revolution

---


