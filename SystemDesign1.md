## System Design

System design is the process of planning, structuring, and defining the architecture of a software system.

---

### Tips and Tricks to Solve System Design Problems

When you are given a System Design Problem, you should approach it in a **planned manner**.  
Initially, the problem may look huge, and one can easily get confused about how to start solving it.  

👉 There is no fixed solution while designing a system.  
👉 There is often more than one way to reach the solution.

---

### Approaching a Design Problem

1. **Breaking Down the Problem**  
2. **Communicating Your Ideas**  
3. **Making Reasonable Assumptions**

---

### Requirements

#### Functional Requirements  
What the system should do.  

**Examples:** login authentication, data input/output, transaction processing.  

#### Non-Functional Requirements  
How the system should operate.  

**Examples:** system scalability, security, response time, reliability, maintainability.  

---

### SOLID Principles

```

S - Single Responsibility Principle
(A class should have only one reason to change)

O - Open Closed Principle
(Software entities should be open for extension, but closed for modification)

L - Liskov Substitution Principle
(Derived classes must be substitutable for their base classes)

I - Interface Segregation Principle
(Do not force clients to implement irrelevant interfaces)

D - Dependency Inversion Principle
(High-level modules should not depend on low-level modules. Both should depend on abstractions)

```

---

### DRY Principle

**Don't Repeat Yourself (DRY)** is a software development principle that encourages developers to avoid duplicating code in a system.

**Ways to Apply DRY:**
- Create functions or methods to encapsulate repeated logic.  
- Use classes and inheritance for reusable components.  
- Extract constants or configurations to central locations.  
- Modularize the code for reusability and maintainability.  

---

### KISS Principle

**Keep It Simple, Stupid** (or *Keep It Short and Simple*) emphasizes simplicity as a key goal in design.

---

### YAGNI Principle

**You Aren’t Gonna Need It (YAGNI)** suggests that developers should only implement features required for the current needs, not hypothetical future requirements.

---

### GRASP Design Principles (OOAD)

In **Object-Oriented Analysis and Design (OOAD)**,  
**General Responsibility Assignment Software Patterns (GRASP)** provide guidelines for assigning responsibilities to classes and objects.  

They promote:
- Low coupling  
- High cohesion  
- Robust and maintainable software systems  

---

### Unified Modeling Language (UML)

- **Structural UML Diagrams**  
- **Behavioral UML Diagrams**

---

### Level Design (LD)

1. **High-Level Design (HLD):**  
   - Defines the overall system architecture  
   - Decides frameworks, databases, integration methods  
   - Focuses on system functionality at a broader level  

2. **Low-Level Design (LLD):**  
   - Details specific components, modules, and interactions  
   - Provides UML diagrams and algorithms  
   - Defines data structures and module behavior  

#### Roadmap to Low-Level Design (LLD)

- STEP 1: Object-Oriented Principles  
- STEP 2: Analyze & Design Process  
- STEP 3: Design Patterns  
- STEP 4: UML Diagrams  
- STEP 5: SOLID Principles  

---

### Design Patterns

System design patterns provide **proven solutions** to common software development problems.

- **Creational Design Patterns**  
- **Structural Design Patterns**  
- **Behavioral Design Patterns**

---
