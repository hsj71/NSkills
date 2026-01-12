# Database Management System (DBMS) – Complete Notes (No Data Skipped)

A **Database Management System (DBMS)** is an organized collection of interrelated data that helps in accessing data quickly, along with efficient insertion and deletion of data into the DBMS. DBMS organizes data in the form of tables, schemas, records, etc.


---

## DBMS over File System

The file system has numerous issues, which were resolved with the help of DBMS. The issues with the file system are:

* **Physical Access Management**: Users are responsible for managing the physical details required to access the database.
* **File System Suitability**: File systems are effective for handling small databases but lack efficiency for larger ones.
* **Concurrency Issues**: For large databases, the operating system struggles to manage concurrency effectively, leading to potential conflicts.
* **Single-User Access**: In a file system, only one user can access the entire dataset at a time, limiting scalability and multi-user functionality.
* **Data Access**: In a file system, accessing data was difficult and insecure as well. Accessing data concurrently was not possible.
* **No Backup and Recovery**: There is no backup and recovery in the file system, which can lead to data loss.

---

## ER Model

### ER Diagram

An ER diagram is a model of a logical view of the database which is represented using the following components:

![components\_of\_er\_diagram](components_of_er_diagram)

### Components of ER Diagram

#### Entity

* A real-world object.
* Represented using a rectangular box.

**Strong Entity**

* Has a primary key.
* All tuples are uniquely identified by the primary key.

**Weak Entity**

* Does not have sufficient attributes to form a primary key.
* Depends on a strong (identifying) entity.
* Represented using a double-lined or bold rectangle.

#### Attribute

* Properties or characteristics of an entity.
* Represented using an oval.

**Key Attribute**

* Determines each entity uniquely.
* Represented using an underlined oval.

**Composite Attribute**

* Formed of multiple attributes.
* Example: Address → state, district, city, street.

**Multivalued Attribute**

* Can have multiple values (e.g., mobile number).
* Represented using a double-lined oval.

**Derived Attribute**

* Derived from other attributes.
* Example: Age from Date of Birth.
* Represented using a dashed oval.

#### Relationship

* Association between two or more entities.
* Represented using a diamond.

---

## Participation Constraint

Participation constraint specifies the minimum or maximum number of relationship instances in which an entity can participate.

### Total Participation

* Every entity participates in at least one relationship.

**Example**:

* In the *Manages* relationship between **Emp** and **Dept**:

  * If every department must have a manager, then **Dept** has total participation.

### Partial Participation

* Some entities participate in the relationship.

**Example**:

* If not all employees are managers, then **Emp** has partial participation.

---

## Cardinality in DBMS

Cardinality of a relation expresses the maximum number of possible relationship occurrences for an entity participating in a relationship.

### Mapping Cardinalities

* **One-to-One (1:1)**
* **One-to-Many (1:N)**
* **Many-to-One (N:1)**
* **Many-to-Many (M:N)**

### Minimum Number of Tables

| Cardinality                                      | Minimum Tables |
| ------------------------------------------------ | -------------- |
| 1:1 (partial participation of both entities)     | 2              |
| 1:1 (total participation of at least one entity) | 1              |
| 1:N                                              | 2              |
| M:N                                              | 3              |

**General Observations**:

* One-to-many or many-to-one → tables can be combined.
* Many-to-many → tables cannot be combined.
* One-to-one with total participation → entity can be merged.
* Total participation of both entities → one table possible.
* Special cases may require extra tables.

---

## Abstraction Techniques

* **Specialization**: Top-down approach; one entity is divided into sub-entities.
* **Generalization**: Bottom-up approach; combines common properties of sub-entities.
* **Aggregation**: Abstraction where relationships are treated as higher-level entities.

![mapping\_cardinalities\_3](mapping_cardinalities_3)

---

## Database Design Goals

* Zero redundancy
* Loss-less join
* Dependency preservation
* Overcome shortcomings of file system

**Codd’s Rule**: All records of a table must be unique.

---

## Integrity Constraints of RDBMS

* **Entity Integrity**: Primary key must be unique and not NULL.
* **Referential Integrity**: Foreign key must match a primary key value.
* **Domain Integrity**: Attribute values must satisfy domain constraints.
* **User-Defined Integrity**: Custom rules defined by users.

---

## Key Terms in Relational Databases

* Table, Record, Field, Domain
* Key, Index, View
* Tuple, Relation
* Cardinality (rows)
* Degree (columns)
* Schema
* Prime Attributes
* Non-Prime Attributes

---

## Keys in Database

### STUDENT Table

| student_id | name    | email                                     | phone      |
| ---------- | ------- | ----------------------------------------- | ---------- |
| 1          | Alice   | [alice@xyz.com](mailto:alice@xyz.com)     | 1234567890 |
| 2          | Bob     | [bob@xyz.com](mailto:bob@xyz.com)         | 9876543210 |
| 3          | Charlie | [charlie@xyz.com](mailto:charlie@xyz.com) | 5555555555 |

### Types of Keys

1. **Primary Key**: student_id
2. **Candidate Keys**: student_id, email, phone
3. **Super Keys**: student_id, student_id+phone, email+phone
4. **Alternate Keys**: email, phone
5. **Foreign Key**: References primary/alternate key of another table

![foreign\_key](foreign_key)

---

## Functional Dependency

Functional Dependency is represented as **A → B**, where A is the determinant and B is the dependent.

### Types of Functional Dependency

* **Trivial**: A → A
* **Non-Trivial**: Student_ID → Student_Name
* **Multivalued**: Student_ID →→ Student_Courses
* **Transitive**: Student_ID → Department

---

## Armstrong’s Axioms

Used to generate attribute closures.

### Attribute Closure Examples

For R(ABCD) {A→B, B→C, C→D}:

* A⁺ = {ABCD}
* B⁺ = {BCD}
* C⁺ = {CD}
* D⁺ = {D}

Superkey = A

For R(ABCDE) {A→BC, CD→E, B→D, E→A}:

* A⁺ = {ABCDE}
* B⁺ = {BD}
* C⁺ = {C}
* D⁺ = {D}
* E⁺ = {ABCDE}

---

## Candidate Key Identification

Steps:

1. Identify all super keys
2. Remove redundant attributes
3. Minimal super key = candidate key

---

## Minimal (Canonical) Cover

Steps:

1. Convert RHS to single attribute
2. Remove unnecessary LHS attributes
3. Remove redundant dependencies

Example:

* AB→C, A→B, BC→A
* Minimal Cover: A→B, B→C, BC→A

---

## Normalization

Eliminates:

* Insertion anomaly
* Deletion anomaly
* Update anomaly

### Normal Forms

#### 1NF

* No multi-valued or composite attributes

#### 2NF

* No partial dependency

#### 3NF

* No transitive dependency

#### BCNF

* LHS of every FD is a super key

| Goal                    | 1NF    | 2NF    | 3NF    | BCNF         |
| ----------------------- | ------ | ------ | ------ | ------------ |
| Redundancy              | High   | Less   | Less   | None         |
| Loss-less               | Always | Always | Always | Always       |
| Dependency Preservation | Always | Always | Always | Sometimes No |

---

## Decomposition Properties

### Loss-less Join Decomposition

If:

```
R1 ⋈ R2 ⋈ ... ⋈ Rn = R
```

Then decomposition is loss-less.

### Dependency Preserving Decomposition

If:

```
F1 ∪ F2 ∪ ... ∪ Fn ≡ F
```

Then decomposition is dependency preserving.

---

## Data Retrieval

### SQL Categories

* **DDL**: CREATE, ALTER, DROP, COMMENT, TRUNCATE
* **DML**: SELECT, INSERT, DELETE, UPDATE, MERGE, CALL
* **DCL**: GRANT, REVOKE

**Note**: Relational model is theoretical; RDBMS is its implementation.

---

## Relational Algebra

### Basic Operators

| Operator | Meaning           |
| -------- | ----------------- |
| σ        | Selection         |
| π        | Projection        |
| ×        | Cartesian Product |
| ∪        | Union             |
| −        | Difference        |
| ρ        | Rename            |

### Extended Operators

* Intersection
* Conditional Join
* Equi Join
* Natural Join
* Left Outer Join
* Right Outer Join
* Full Outer Join
* Division (/)

---

## Relational Calculus

### Tuple Relational Calculus

```
{t | cond(t)}
```

### Domain Relational Calculus

```
{x1, x2, ..., xn | cond(x1, x2, ..., xn)}
```

---

## SQL Commands

| Command  | Meaning        |
| -------- | -------------- |
| SELECT   | Select columns |
| FROM     | Specify tables |
| WHERE    | Filter rows    |
| GROUP BY | Group tuples   |
| ORDER BY | Sort output    |
| HAVING   | Filter groups  |
| UPDATE   | Update rows    |
| DELETE   | Delete rows    |

Example:

```sql
SELECT COUNT(*) FROM student GROUP BY dept_id;
```

---

## File Organization

* Sequential File Organization
* Heap File Organization
* Hash File Organization
* B+ Tree File Organization
* Clustered File Organization

### Blocking Factor

```
⌊ Block Size / Record Size ⌋
```

---

## Indexing

### Single-Level Index

* Primary Index (Sparse)
* Secondary Index (Dense)
* Clustered Index

### Multi-Level Index

* Indexed Sequential Access Method
* Number of block accesses = n + 1

---

## B-Tree

* Balanced search tree
* Keys and data pointers at each node
* All leaf nodes at same level

### B+ Tree

* All records stored at leaf level
* Leaf nodes linked
* Supports sequential and random access

---

## Transactions

A transaction is a logical unit of work.

### ACID Properties

* Atomicity
* Consistency
* Isolation
* Durability

---

## Transaction States

* Active
* Partially Committed
* Committed
* Failed
* Aborted

![Transaction Flow](dbms_2-22)

---

## Schedules

* Serial Schedule (n!)
* Non-Serial Schedule

### Serializability

* Conflict Serializability
* View Serializability

---

## Recoverability Types

* Irrecoverable Schedule
* Recoverable Schedule
* Cascadeless Schedule
* Strict Recoverable Schedule

---

## Concurrency Control

Concurrency control ensures that database transactions execute safely while maintaining **consistency** when multiple transactions run simultaneously.

### Problems Solved by Concurrency Control

* Lost Update Problem
* Dirty Read Problem
* Unrepeatable Read Problem
* Inconsistent Analysis Problem

---

### Lock-Based Concurrency Control

A **lock** is a mechanism used to control access to a database item.

#### Types of Locks

1. **Binary Lock**

   * Locked (1) or Unlocked (0)
   * Very restrictive

2. **Shared Lock (S-Lock)**

   * Used for read operations
   * Multiple transactions can hold S-lock on the same data item

3. **Exclusive Lock (X-Lock)**

   * Used for write operations
   * Only one transaction can hold X-lock

---

## Two Phase Locking Protocol (2PL)

The **Two Phase Locking Protocol (2PL)** ensures **conflict serializability** of schedules.

### Phases of 2PL

1. **Growing Phase**

   * Transaction can **acquire locks**
   * Transaction **cannot release** any lock

2. **Shrinking Phase**

   * Transaction can **release locks**
   * Transaction **cannot acquire** any new lock

Once a transaction releases a lock, it cannot request any new lock.

---

### Rules of Two Phase Locking

* All locking operations must precede unlocking operations
* A transaction must acquire a lock before accessing a data item
* Lock upgrade (S → X) is allowed only during the growing phase
* Lock downgrade (X → S) is allowed only during the shrinking phase

---

### Types of Two Phase Locking

#### 1. Basic Two Phase Locking (Basic 2PL)

**Rules**:

* Follows growing and shrinking phases strictly
* Locks can be released before transaction commits

**Advantages**:

* Ensures conflict serializability

**Disadvantages**:

* May lead to **cascading rollbacks**
* Does not guarantee recoverability

---

#### 2. Strict Two Phase Locking (Strict 2PL)

**Rules**:

* All **exclusive (X) locks** are held until the transaction commits or aborts
* Shared locks can be released earlier

**Properties**:

* Prevents dirty reads
* Ensures **strict schedules**

**Advantages**:

* No cascading rollback
* Ensures recoverability

---

#### 3. Rigorous Two Phase Locking (Rigorous 2PL)

**Rules**:

* Both **shared (S) and exclusive (X) locks** are held until commit or abort

**Properties**:

* Transactions release all locks together at commit time

**Advantages**:

* Stronger than Strict 2PL
* Simplifies recovery

**Disadvantages**:

* Lower concurrency

---

#### 4. Conservative Two Phase Locking (Static 2PL)

**Rules**:

* Transaction must acquire **all required locks before execution begins**
* If any lock is unavailable, transaction waits

**Properties**:

* No growing/shrinking during execution

**Advantages**:

* **Deadlock-free**

**Disadvantages**:

* Low resource utilization
* Difficult to predict all required locks in advance

---

## Deadlock

A **deadlock** occurs when two or more transactions wait indefinitely for each other to release locks.

### Deadlock Handling Techniques

* Deadlock Prevention
* Deadlock Avoidance
* Deadlock Detection and Recovery

---

## Timestamp Ordering Protocol

* Read Rule
* Write Rule

### Thomas Write Rule

* Ignores outdated writes
* Prevents unnecessary aborts
* Allows higher concurrency
