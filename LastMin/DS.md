# Data Structures

Data structures are ways to organize and store data so it can be used efficiently. They are essential in computer science for managing and processing information in programs. Common types of data structures include arrays, linked lists, stacks, queues, trees, and graphs. Each structure is designed for specific tasks, such as searching, sorting, or managing hierarchical data. Understanding data structures helps in solving problems faster and writing better algorithms.

Data structures are of two types:

1. **Linear Data Structures:** Elements are arranged sequentially. Each element is connected to its previous and next element.
2. **Non-Linear Data Structures:** Elements are connected in a hierarchical or network-like structure.

---

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

An array is a data structure used to store multiple elements of the same type in contiguous memory locations. Arrays are simple and widely used.

**Declaration in C:**

```c
int arr[10];          // by size
int arr[] = {10,20};  // by initializing
int arr[6] = {10,20,30,40}; // size + initialization
```

**Initialization:**

```c
int arr[5] = {1,2,3,4,5};
```

**Accessing Elements:**

```c
arr[0] = 10;          // Assigns 10 to the first element
printf("%d", arr[2]); // Prints the third element
```

**Formulas:**

* Length of Array = UB - LB + 1

**Types of Arrays:**

* One-Dimensional Array

```c
int arr[5] = {10,20,30,40,50};
```

* Multi-Dimensional Array

```c
int matrix[2][3] = {
    {1,2,3},
    {4,5,6}
};
```

**Address Calculation:**

```
Loc(arr[k]) = base(arr) + w * k
w = number of bytes per element
k = index of the element
```

**Storage Orders:**

* Column Major: Loc(arr[i][j]) = base(arr) + w * (m*j + i)
* Row Major: Loc(arr[i][j]) = base(arr) + w * (n*i + j)

**Operations:** Traversal, Insertion, Deletion, Searching, Sorting

read more about - Arrays

---

## Stacks

A stack is a linear data structure that follows **LIFO (Last In, First Out)**.

**Basic Operations:**

1. Push: Add item. O(1)
2. Pop: Remove item. O(1)
3. Peek: Retrieve top element. O(1)

**Notations:**

* Infix: `A * (B + C) / D`
* Postfix: `A B C + * D /`
* Prefix: `/ * A + B C D`

**Implementation:** Arrays, Linked Lists

**Example Problem: Tower of Hanoi**

* Move disks obeying size rules
* Total moves = 2^n - 1
* Time Complexity = O(2^n)

read more about - Stacks

---

## Queues

Queue follows **FIFO (First In, First Out)**.

**Types:** Simple, Circular, Priority, Deque

**Operations:** Enqueue, Dequeue, Peek, Traversal, Front, Rear

**Implementation:** Arrays, Linked Lists

read more about - Queues

---

## Linked Lists

Linear structure where nodes point to next nodes using pointers.

**Types:** Singly, Doubly, Circular, Doubly Circular

**Operations:** Traversal, Insertion, Deletion, Search

**Node Representation in C:**

```c
struct node {
    int data;
    struct node *next;
};
```

Advantages: Dynamic, flexible, easy insertion/deletion
Drawbacks: No random access, extra pointer memory

read more about - Linked List

---

## Tree

Non-linear hierarchical structure with nodes connected by edges.

**Terminology:** Node, Edge, Degree, Binary Tree, Path

**Types:** General, Binary, BST, Balanced BST, Complete, Full, Heap, Trie, N-ary

**Traversal Techniques:**

* Inorder (Left, Root, Right)
* Preorder (Root, Left, Right)
* Postorder (Left, Right, Root)
* Level Order (BFS)

BST operations: Insertion, Deletion, Search, Traversal

read more about - Binary Search Tree

---

## Heap

Tree-based data structure: Max-Heap / Min-Heap

**Operations:** Insertion, Deletion, Heapify, Heap Sort (O(n log n))

read more about - Heap

---

## AVL Tree

Self-balancing BST with balance factor <= 1

**Rotations:** LL, RR, LR, RL

**Time Complexities:**

| Operation          | Binary Tree | BST      | Heap            | AVL Tree |
| ------------------ | ----------- | -------- | --------------- | -------- |
| Insertion          | O(1)        | O(log n) | O(log n)        | O(log n) |
| Deletion           | O(1)        | O(log n) | O(log n)        | O(log n) |
| Search             | O(n)        | O(log n) | O(n) (unsorted) | O(log n) |
| Traversal          | O(n)        | O(n)     | O(n)            | O(n)     |
| Balance Check      | O(n)        | O(n)     | N/A             | O(log n) |
| Height Calculation | O(n)        | O(n)     | O(n)            | O(log n) |

read more about - AVL Tree

---

## Graphs

Non-linear structure: vertices and edges.

**Traversal:** DFS, BFS

**DFS Example:**

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

**BFS Example:**

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

Mapping data to fixed-size values using a hash function.

**Terminology:** Key, Hash Value, Bucket, Loa
