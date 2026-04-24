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

# new code 2 Buildings with Sunlight
```
Buildings with Sunlight
Given the array arr[] of heights of certain buildings that lie adjacent to each other, Sunlight starts falling from the left side of the buildings. If there is a building of a certain height, all the buildings to the right side of it having lesser heights cannot see the sun.

Find the total number of buildings that receive sunlight.

Examples:

Input: arr[] = [6, 2, 8, 4, 11, 13]
Output: 4
Explanation: Only the buildings with heights 6, 8, 11, and 13 receive sunlight; therefore, the output is 4.
  
Input: arr[] = [2, 5, 1, 8, 3]
Output: 3
Explanation: Only buildings of height 2, 5 and 8 can see the sun, hence output is 3.
  
Input: arr[] = [3, 3, 3, 1]
Output: 3
Explanation: The first three buildings (height 3) receive sunlight, while the last building (1) is blocked. Hence, the output is 3.
Constraints:
1 ≤ arr.size() ≤ 105
1 ≤ arr[i] ≤ 105
```
```
class Solution:
    def visibleBuildings(self, arr):
        # code here
        count = 0
        max_height = 0
        
        for height in arr:
            if (height > max_height or height == max_height):
                count += 1
                max_height = height
        
        return count

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
