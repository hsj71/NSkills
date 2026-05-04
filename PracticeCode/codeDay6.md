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
 
# new code 2 Position of the Set Bit
```
Position of the Set Bit
Given an integer n, determine position of the only set bit (1) in its binary representation. The position is counted starting from 1 at the least significant bit (LSB).

If n contains exactly one set bit, return its position.
If n contains no set bits or more than one set bit, return -1.
Examples:

Input: n = 2
Output: 2
Explanation: 2 is represented as "10" in binary. It has only one set bit, which is at position 2.
Input: n = 5
Output: -1
Explanation: 5 is represented as "101" in binary. It has two set bits; therefore, the output is -1.
Constraints:
0 ≤ n ≤ 108
```
```
class Solution:
    def findPosition(self, n):
        # code here 
        if (n & (n-1)) != 0 :
            return -1
        i = 0
        while n :
            n = n >> 1
            i += 1
        return i
```
---

# new code 3 Palindrome Binary
```
Palindrome Binary
Given an integer n, determine whether its binary representation forms a palindrome. Return true if the binary representation of n is a palindrome; otherwise, return false.

Note: A binary representation is considered a palindrome if it reads the same forward and backward.

Examples:

Input: n = 17
Output: true
Explanation: Binary representation of 17 is (10001)2, which reads the same forward and backward, so it is a palindrome. 
Input: n = 16
Output: false
Explanation: Binary representation of 16 is (10000)2, which is not a palindrome. 
Constraints:
1 ≤ n ≤ 109
```
```
class Solution:
    def isBinaryPalindrome(self, n):
        # code here
        s=""
        while n>0:
            if n%2==0:
                s="0"+s
            else:
                s="1"+s
            n>>=1
        if s==s[::-1]:
            return True
        return False
        '''
        a=bin(n).replace("0b","")
        if a==a[::-1]:
            return True
        else:
            return False'''
```
---

# new code 4
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

