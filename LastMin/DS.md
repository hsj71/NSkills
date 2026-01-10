# Data Structures

Data structures are ways to organize and store data so it can be used efficiently. They are essential in computer science for managing and processing information in programs. Common types of data structures include arrays, linked lists, stacks, queues, trees, and graphs. Each structure is designed for specific tasks, such as searching, sorting, or managing hierarchical data. Understanding data structures helps in solving problems faster and writing better algorithms.

---

## Types of Data Structures

1. **Linear Data Structures**: In linear data structures, elements are arranged in a sequential order. Each element is connected to its previous and next element, making traversal straightforward.

2. **Non-Linear Data Structures**: In non-linear data structures, elements are not arranged sequentially. They are connected in a hierarchical or network-like structure.

---

## Table of Contents

* Arrays
* Stacks
* Queues
* Linked Lists
* Tree
* Graphs
* Hashing

---

## Arrays

An array is a data structure used to store multiple elements of the same type in contiguous memory locations. Arrays are simple and widely used for organizing and managing data.

### Declaration

```c
// Array declaration by specifying size
int arr[10];

// Array declaration by initializing elements
int arr[] = {10, 20, 30, 40};

// Array declaration by specifying size and initializing elements
int arr[6] = {10, 20, 30, 40};
```

### Initialization

```c
int arr[5] = {1, 2, 3, 4, 5};
```

### Accessing Elements

```c
arr[0] = 10;          // Assigns 10 to the first element
printf("%d", arr[2]); // Prints the third element
```

### Formulas

```
Length of Array = UB - LB + 1
```

### Types of Arrays

1. **One-Dimensional Array**: Stores elements in a single row.

```c
int arr[5] = {10, 20, 30, 40, 50};
```

2. **Multi-Dimensional Array**: Represents a matrix or table of data.

```c
int matrix[2][3] = {
     {1, 2, 3},
     {4, 5, 6}
};
```

### Address Calculation

```
Loc(arr[k]) = base(arr) + w * k
w = number of bytes per storage location of one element
k = index of array whose address we want to calculate
```

### Storage Orders for 2D Arrays

* **Column Major Order**:

```
Loc(arr[i][j]) = base(arr) + w * (m * j + i)
```

* **Row Major Order**:

```
Loc(arr[i][j]) = base(arr) + w * (n * i + j)
```

### Common Operations on Arrays

* Traversal
* Insertion
* Deletion
* Searching (Linear & Binary Search)
* Sorting (Bubble Sort, Selection Sort, Quick Sort)

[Read more about Arrays]

---

## Stacks

A stack is a linear data structure that follows the Last In, First Out (LIFO) principle.

### Basic Operations

1. **Push**: Adds an item to the stack. Time Complexity: O(1)
2. **Pop**: Removes the top item. Time Complexity: O(1)
3. **Peek**: Retrieves the top element without removing it. Time Complexity: O(1)

### Notations

* Infix: `A * (B + C) / D`
* Postfix: `A B C + * D /`
* Prefix: `/ * A + B C D`

### Implementation

* Arrays
* Linked Lists
* Tower of Hanoi (Mathematical Puzzle)

Time Complexity for Tower of Hanoi: O(2^n)

[Read more about Stacks]

---

## Queues

A queue follows the First In, First Out (FIFO) principle.

### Types of Queues

* Simple Queue
* Circular Queue
* Priority Queue
* Deque (Double-Ended Queue)

### Operations

* Enqueue
* Dequeue
* Peek
* Traversal
* Front & Rear Access

### Implementation

* Arrays
* Linked Lists

[Read more about Queues]

---

## Linked Lists

A linked list is a linear data structure with nodes connected using pointers.

### Types

* Singly Linked List
* Doubly Linked List
* Circular Linked List
* Doubly Circular Linked List

### Operations

* Traversal
* Insertion
* Deletion
* Search

### Advantages

* Dynamic Memory Allocation
* Ease of insertion/deletion
* Flexible Size

### Drawbacks

* No random access
* Extra memory for pointers

### Node Representation in C

```c
struct node {
  int data;
  struct node *next;
};
```

[Read more about Linked List]

---

## Tree

A tree is a non-linear hierarchical data structure.

### Terminology

* Node, Edge, Degree, Path, Binary Tree

### Types

* General Tree
* Binary Tree
* Binary Search Tree (BST)
* Balanced Binary Tree (AVL, Red-Black)
* Complete Binary Tree
* Full Binary Tree
* Heap (Min/Max)
* Trie
* N-ary Tree

### Traversals

* Inorder
* Preorder
* Postorder
* Level Order (BFS)

[Read more about Binary Search Tree]

---

## Heap

Special tree-based structure that satisfies max-heap or min-heap property.

### Operations

* Insertion
* Deletion (Root)
* Heapify
* Heap Sort

[Read more about Heap]

---

## AVL Tree

Self-balancing binary search tree with rotations to maintain height balance.

### Rotations

* Left-Left (LL)
* Right-Right (RR)
* Left-Right (LR)
* Right-Left (RL)

### Operations Time Complexity Table

| Operation          | Binary Tree | BST      | Heap     | AVL Tree |
| ------------------ | ----------- | -------- | -------- | -------- |
| Insertion          | O(1)        | O(log n) | O(log n) | O(log n) |
| Deletion           | O(1)        | O(log n) | O(log n) | O(log n) |
| Search             | O(n)        | O(log n) | O(n)     | O(log n) |
| Traversal          | O(n)        | O(n)     | O(n)     | O(n)     |
| Balance Check      | O(n)        | O(n)     | N/A      | O(log n) |
| Height Calculation | O(n)        | O(n)     | O(n)     | O(log n) |

[Read more about AVL Tree]

---

## Graphs

Non-linear data structure with vertices and edges.

### Traversal Techniques

* Depth First Search (DFS)
* Breadth First Search (BFS)

[Read more about Graphs]

---

## Hashing

Technique to map data of arbitrary size to fixed-size hash values.

### Terminology

* Key, Hash Value, Bucket, Load Factor

### Collision Resolution Techniques

* Chaining
* Open Addressing (Linear, Quadratic, Double Hashing)

[Read more about Hashing]
