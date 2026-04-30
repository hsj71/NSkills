# new code 1 Check if an Array is Max Heap
```
Check if an Array is Max Heap
Given an array arr[], determine whether it represents the level-order traversal of a valid max heap. Return true if it does; otherwise, return false.

Examples :

Input: arr[] = [90, 15, 10, 7, 12, 2]
Output: true
Explanation: The given array represents the following tree. Each parent node is greater than or equal to its children, so the max-heap property holds.
 
Input: arr[] = [9, 15, 10, 7, 12, 11]
Output: false
Explanation: The given array represents the following tree. It does not satisfy the max-heap property, as 9 is smaller than 15 and 10, and 10 is smaller than 11.
 
Constraints:
1 ≤ n ≤ 105
1 ≤ arr[i] ≤ 105
```
```
class Solution:
    def isMaxHeap(self, arr):
        # code here
        n = len(arr)

        # Check all parent nodes
        for i in range(n // 2):
            left = 2 * i + 1
            right = 2 * i + 2

            # Check left child
            if left < n and arr[i] < arr[left]:
                return False

            # Check right child
            if right < n and arr[i] < arr[right]:
                return False

        return True
```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

# new code 1
```

```
```

```
---

