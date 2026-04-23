# new code 1 Two Equal Sum Subarrays
```
Two Equal Sum Subarrays
Given an array of integers arr[], return true if it is possible to split it in two subarrays (without reordering the elements), such that the sum of the two subarrays are equal. If it is not possible then return false.

Examples:

Input: arr[] = [1, 2, 3, 4, 5, 5]
Output: true
Explanation: We can divide the array into [1, 2, 3, 4] and [5, 5]. The sum of both the subarrays are 10.
Input: arr[] = [4, 3, 2, 1]
Output: false
Explanation: We cannot divide the array into two subarrays with equal sum.
Constraints:
1 ≤ arr.size() ≤ 105 
1 ≤ arr[i] ≤ 106


```
```
class Solution:
    def canSplit(self, arr):
        #code here
        total = sum(arr)
        
        # if total sum is odd, split cannot equally
        if total % 2 != 0:
            return False
            
        target = total // 2
        prefix_sum = 0
        
        for i in range(len(arr)):
            prefix_sum += arr[i]
            
            # Check if we found a valid split point
            if prefix_sum == target:
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
