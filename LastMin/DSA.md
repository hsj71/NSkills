# Algorithms and Data Structures

## Algorithm

An algorithm is a step-by-step procedure or set of rules to solve a specific problem. It is a logical sequence of instructions designed to achieve a desired output for given inputs.

## Analysis of Algorithm

1. **Worst Case Analysis (Usually Done):** In the worst case analysis, we calculate upper bound on running time of an algorithm by considering worst case (a situation where algorithm takes maximum time).

2. **Average Case Analysis (Sometimes Done):** In average case analysis, we take all possible inputs and calculate computing time for all of the inputs.

3. **Best Case Analysis (Bogus):** In the best case analysis, we calculate lower bound on running time of an algorithm.

## Table of Content

* Asymptotic Notations
* Sorting
* Searching
* Trees
* Graph
* Divide and Conquer
* Greedy Approach
* Dynamic Programming
* Backtracking

## Asymptotic Notations

### Θ Notation

The theta notation bounds a function from above and below, so it defines exact asymptotic behavior.

```
Θ(g(n)) = {f(n): there exist positive constants c1, c2 and n0 such that 0 <= c1*g(n) <= f(n) <= c2*g(n) for all n >= n0}
```

### Big O Notation

The Big O notation defines an upper bound of an algorithm, it bounds a function only from above.

```
O(g(n)) = { f(n): there exist positive constants c and n0 such that 0 <= f(n) <= cg(n) for all n >= n0}
```

### Ω Notation

Just as Big O notation provides an asymptotic upper bound on a function, Ω notation provides an asymptotic lower bound.

```
Ω(g(n)) = {f(n): there exist positive constants c and n0 such that 0 <= cg(n) <= f(n) for all n >= n0}
```

Read more about - Asymptotic Notations

## Solving Recurrences

### Substitution Method

We make a guess for the solution and then we use mathematical induction to prove the guess is correct or incorrect.

### Recurrence Tree Method

We draw a recurrence tree and calculate the time taken by every level of tree. Finally, we sum the work done at all levels.

### Master Theorem Method

Only for the following type of recurrences or for recurrences that can be transformed to the following type:

```
T(n) = aT(n/b) + f(n) where a >= 1 and b > 1
```

## Sorting

| Algorithm | Worst Case | Average Case | Best Case  | Min. no. of swaps | Max. no. of swaps |
| --------- | ---------- | ------------ | ---------- | ----------------- | ----------------- |
| Bubble    | Θ(n²)      | Θ(n²)        | Θ(n)       | 0                 | Θ(n²)             |
| Selection | Θ(n²)      | Θ(n²)        | Θ(n²)      | 0                 | Θ(n)              |
| Insertion | Θ(n²)      | Θ(n²)        | Θ(n)       | 0                 | Θ(n²)             |
| Quick     | Θ(n²)      | Θ(n log n)   | Θ(n log n) | 0                 | Θ(n²)             |
| Merge     | Θ(n log n) | Θ(n log n)   | Θ(n log n) | Is not in-place   | Is not in-place   |
| Heap      | Θ(n log n) | Θ(n log n)   | Θ(n log n) | O(n log n)        | Θ(n log n)        |

## Searching

| Algorithm     | Worst Case | Average Case | Best Case |
| ------------- | ---------- | ------------ | --------- |
| Linear Search | Θ(n)       | Θ(n)         | Θ(1)      |
| Binary Search | O(log n)   | O(log n)     | O(1)      |

## Trees

Unlike Arrays, Linked Lists, Stack, and Queues, which are linear data structures, trees are hierarchical data structures.

### Depth First Traversal

* Inorder: Visit left subtree, root, right subtree.
* Preorder: Visit root, left subtree, right subtree.
* Postorder: Visit left subtree, right subtree, root.

### Binary Search Tree (BST)

Binary Search Tree is a node-based binary tree data structure which has the following properties:

* The left subtree of a node contains only nodes with keys less than the node’s key.
* The right subtree of a node contains only nodes with keys greater than the node’s key.
* The left and right subtree each must also be a binary search tree.
* There must be no duplicate nodes.
* Supports Insertion and Deletion.

### AVL Tree

AVL tree is a self-balancing Binary Search Tree (BST) where the difference between heights of left and right subtrees cannot be more than one for all nodes.

* Supports Insertion and Deletion.

### B-Tree

B-Tree is a self-balancing search tree. In most of the other self-balancing search trees, it is assumed that everything is in main memory. To understand use of B-Trees, we must think of huge amount of data that cannot fit in main memory. When the number of keys is high, the data is read from disk in the form of blocks. Disk access time is very high compared to main memory access time. The main idea of using B-Trees is to reduce the number of disk accesses.

* Properties of Prim’s Minimum Spanning Tree Algorithm
* Supports B-Tree Insertion and B-Tree Deletion.

### Minimum Spanning Tree (MST)

Minimum Spanning Tree (MST) problem: Given a connected graph G with positive edge weights, find a minimum weight set of edges that connects all of the vertices. MST is a fundamental problem with diverse applications:

* Network design– telephone, electrical, hydraulic, TV cable, computer, road.
* Approximation algorithms for NP-hard problems – traveling salesperson problem, Steiner tree.
* Cluster analysis- k clustering problem can be viewed as finding an MST and deleting the k-1 most expensive edges.

**Example:** Kruskal’s Minimum Spanning Tree Algorithm.

## Graph

Graph is a data structure that consists of following two components:

1. A finite set of vertices also called nodes.
2. A finite set of ordered pair of the form (u, v) called edge. The pair is ordered because (u, v) is not same as (v, u) in case of directed graph (di-graph). The edges may contain weight/value/cost.

### Representations

* **Adjacency Matrix:** 2D array of size V x V where V is the number of vertices in a graph.
* **Adjacency List:** An array of linked lists is used. Size of the array is equal to number of vertices.

### Graph Algorithms

| Algorithm                     | Time Complexity                   |
| ----------------------------- | --------------------------------- |
| Breadth First Traversal (BFS) | O(V+E) (list), O(V²) (matrix)     |
| Depth First Traversal (DFS)   | O(V+E) (list), O(V²) (matrix)     |
| Dijkstra’s shortest path      | O(V²) (matrix), O(E log V) (list) |
| Topological Sorting           | O(V+E)                            |

## Divide and Conquer

Steps:

1. Divide: Break the given problem into subproblems of same type.
2. Conquer: Recursively solve these subproblems.
3. Combine: Appropriately combine the answers.

Time Complexity Analysis:
If a problem of size n is divided into k subproblems, each of size n/m, and the merging step takes O(f(n)), the time complexity is given by the Master Theorem:

```
T(n) = kT(n/m) + O(f(n))
```

### Standard Divide and Conquer Algorithms

1. **Binary Search:** Divide search space into halves, compare middle element, recursively search in relevant half. Time Complexity: O(log n)
2. **Quicksort:** Picks pivot, rearranges array elements around pivot, recursively sorts subarrays. Time Complexity: Best/Average O(n log n), Worst O(n²)
3. **Merge Sort:** Divide array in halves, recursively sort, merge. Time Complexity: O(n log n)
4. **Closest Pair of Points:** Find closest pair in x-y plane. Brute-force O(n²), Divide and Conquer O(n log n)
5. **Strassen's Matrix Multiplication:** Divide matrices, recursive multiplications, combine results. Time Complexity: O(n².81)

## Greedy Approach

Greedy builds a solution piece by piece, choosing the next piece offering the most obvious benefit. Used for optimization problems.

### Standard Greedy Algorithms

1. **Kruskal’s MST:** Pick smallest weight edge not causing cycle. Time Complexity: O(E log V)
2. **Prim’s MST:** Pick smallest weight edge connecting included and not included sets. Time Complexity: O(E log V)
3. **Dijkstra’s Shortest Path:** Similar to Prim’s. Pick edge connecting two sets with smallest path. Time Complexity: O((V + E) log V)
4. **Huffman Coding:** Assign variable length codes, least bit code to most frequent. Time Complexity: O(n log n)

Read more about - Greedy Approach

## Dynamic Programming (DP)

Breaks problem into smaller overlapping subproblems, solves each once, stores solution to avoid redundant computations. Useful for optimization problems.

### Steps

1. Define Subproblems
2. Recurrence Relation
3. Base Case
4. Solve and Store (memoization/tabulation)
5. Construct Solution

### Examples

1. **Fibonacci Numbers:** Compute nth number. Recurrence: F(n) = F(n-1) + F(n-2). Time Complexity: O(n)
2. **Longest Common Subsequence (LCS):** Find longest common subsequence between two strings. Recurrence: LCS(X, Y, i, j) = 1 + LCS(X, Y, i-1, j-1) if X[i] == Y[j], else max(LCS(X, Y, i-1, j), LCS(X, Y, i, j-1)). Time Complexity: O(m * n)
3. **Knapsack Problem:** Maximize value in knapsack of capacity W. Recurrence: K(i, W) = max(K(i-1, W), K(i-1, W-w[i]) + v[i]). Time Complexity: O(n * W)
4. **Matrix Chain Multiplication:** Minimize scalar multiplications. Recurrence: M(i, j) = min(M(i, k) + M(k+1, j) + p[i-1]*p[k]*p[j]). Time Complexity: O(n³)

Read more about - Dynamic Programming

## Backtracking

Algorithmic technique exploring all possible solutions incrementally, abandoning solutions that fail constraints.

### Steps

1. Choose: Make a choice.
2. Explore: Recursively explore solutions.
3. Backtrack: Undo last choice if invalid.

### Examples

1. **N-Queens Problem:** Place N queens on N x N board so no two queens threaten each other.
2. **Sudoku Solver:** Fill 9x9 grid with 1-9 numbers, each row, column, and 3x3 sub-grid unique.
3. **Subset Sum Problem:** Determine if subset of given set sums to target value.
4. **Generating Permutations:** Generate all permutations of a string or array by recursive swapping and backtracking.
