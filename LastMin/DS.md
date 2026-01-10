# Data Structures

Data structures are ways to organize and store data so it can be used efficiently. They are essential in computer science for managing and processing information in programs. Common types of data structures include arrays, linked lists, stacks, queues, trees, and graphs. Each structure is designed for specific tasks, such as searching, sorting, or managing hierarchical data. Understanding data structures helps in solving problems faster and writing better algorithms.

## Types of Data Structures

1. **Linear Data Structures**: In linear data structures, elements are arranged in a sequential order. Each element is connected to its previous and next element, making traversal straightforward.
2. **Non-Linear Data Structures**: In non-linear data structures, elements are not arranged sequentially. They are connected in a hierarchical or network-like structure.

## Table of Content

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
arr[0] = 10;  // Assigns 10 to the first element
printf("%d", arr[2]);  // Prints the third element
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
w = number of bytes per element
k = index of array element
```

#### Two-Dimensional Arrays Storage

* **Column Major Order**:

```
Loc(arr[i][j]) = base(arr) + w * (m * j + i)
```

* **Row Major Order**:

```
Loc(arr[i][j]) = base(arr) + w * (n * i + j)
```

### Common Operations

* **Traversal**:

```c
for (int i = 0; i < 5; i++) {
     printf("%d ", arr[i]);
}
```

* **Insertion, Deletion, Searching, Sorting**
* **Linear Search**: O(n)
* **Binary Search**: O(log n) (requires sorted array)
* Sorting algorithms: Bubble Sort, Selection Sort, Quick Sort

read more about - Arrays

---

## Stacks

A stack is a linear data structure that follows the Last In, First Out (LIFO) principle.

### Basic Operations

1. **Push**: Adds an item to the stack. Time Complexity: O(1)
2. **Pop**: Removes the top item. Time Complexity: O(1)
3. **Peek**: Retrieves the top element without removing it. Time Complexity: O(1)

### Notations

* **Infix**: X + Y (operators between operands)
* **Postfix (Reverse Polish)**: XY+ (operators after operands)
* **Prefix (Polish)**: +XY (operators before operands)

### Implementation

* Arrays
* Linked Lists

### Tower of Hanoi

Rules:

* Move one disk at a time
* Only top disk can be moved
* No disk may be placed on smaller disk
* Moves required: 2^n - 1
* Time complexity: O(2^n)

read more about - Stacks

---

## Queues

A queue follows First In, First Out (FIFO) principle.

### Types of Queues

* Simple Queue
* Circular Queue
* Priority Queue
* Deque (Double-Ended Queue)

### Operations

* **Enqueue**: Add item
* **Dequeue**: Remove item
* **Peek**: Get front element
* **Traversal**: Iterate through all elements

### Implementation

* Arrays
* Linked Lists

read more about - Queues

---

## Linked Lists

A linked list is a linear data structure where elements (nodes) are connected using pointers.

### Types

* Singly Linked List
* Doubly Linked List
* Circular Linked List
* Doubly Circular Linked List

### Operations

* Traversal: O(n)
* Insertion: O(1) at beginning, O(n) elsewhere
* Deletion: O(1) at beginning, O(n) elsewhere
* Search: O(n)

### Advantages

* Dynamic memory allocation
* Flexible size

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

read more about - Linked List

---

## Tree

A tree is a non-linear hierarchical data structure.

### Terminology

* Node, Edge, Degree, Path, Binary Tree

### Types of Trees

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

* **Inorder (L, Root, R)**
* **Preorder (Root, L, R)**
* **Postorder (L, R, Root)**
* **Level Order (BFS)**

### BST Operations

* Insertion
* Deletion (leaf, one child, two children)
* Search

### Heap

* Max-Heap / Min-Heap
* Operations: Insertion, Deletion, Heapify, Heap Sort

### AVL Tree

* Self-balancing BST
* Rotations: LL, RR, LR, RL

| Operation          | Binary Tree | BST      | Heap     | AVL      |
| ------------------ | ----------- | -------- | -------- | -------- |
| Insertion          | O(1)        | O(log n) | O(log n) | O(log n) |
| Deletion           | O(1)        | O(log n) | O(log n) | O(log n) |
| Search             | O(n)        | O(log n) | O(n)     | O(log n) |
| Traversal          | O(n)        | O(n)     | O(n)     | O(n)     |
| Balance Check      | O(n)        | O(n)     | N/A      | O(log n) |
| Height Calculation | O(n)        | O(n)     | O(n)     | O(log n) |

read more about - AVL Tree

---

## Graphs

A graph consists of vertices and edges connecting pairs of vertices.

### Traversals

1. **DFS**

```c
void DFS(int vertex, int visited[], int graph[][V]) {
     printf("%d ", vertex);
     visited[vertex] = 1;
     for (int i = 0; i < V; i++) {
         if (graph[vertex][i] == 1 && !visited[i]) {
             DFS(i, visited, graph);
         }
     }
}
```

2. **BFS**

```c
void BFS(int start, int graph[][V]) {
    int visited[V] = {0};
    int queue[V], front = 0, rear = 0;

    queue[rear++] = start;
    visited[start] = 1;

    while (front != rear) {
        int current = queue[front++];
        printf("%d ", current);

        for (int i = 0; i < V; i++) {
            if (graph[current][i] == 1 && !visited[i]) {
                queue[rear++] = i;
                visited[i] = 1;
            }
        }
    }
}
```

read more about - Graphs

---

## Hashing

Hashing maps data of arbitrary size to fixed-size hash values.

### Terminology

* Key, Hash Value, Bucket, Load Factor

### Collision Resolution

1. **Chaining**: Linked list in each bucket
2. **Open Addressing**: Linear, Quadratic, Double Hashing

```c
Linear Probing: index = (hash + i) % table_size
Quadratic Probing: index = (hash + i^2) % table_size
Double Hashing: index = (hash1 + i * hash2) % table_size
```
