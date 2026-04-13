## new problem 1 ( Array Leaders )
```
Array Leaders
Difficulty: EasyAccuracy: 29.94%Submissions: 987K+Points: 2Average Time: 15m
You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.

Examples:

Input: arr = [16, 17, 4, 3, 5, 2]
Output: [17, 5, 2]
Explanation: Note that there is nothing greater on the right side of 17, 5 and, 2.
Input: arr = [10, 4, 2, 4, 1]
Output: [10, 4, 4, 1]
Explanation: Note that both of the 4s are in output, as to be a leader an equal element is also allowed on the right. side
Input: arr = [5, 10, 20, 40]
Output: [40]
Explanation: When an array is sorted in increasing order, only the rightmost element is leader.
Input: arr = [30, 10, 10, 5]
Output: [30, 10, 10, 5]
Explanation: When an array is sorted in non-increasing order, all elements are leaders.
Constraints:
1 <= arr.size() <= 106
0 <= arr[i] <= 106
```
```
class Solution:
    def leaders(self, arr):
        # code here
        res=[]
        m=arr[-1]
        for i in range(len(arr)-1,-1,-1):
            if arr[i]>=m:
                m=arr[i]
                res.append(arr[i])
        return res[::-1]

```
---

## new problem 2 ( Majority Element )
```
Majority Element
Difficulty: MediumAccuracy: 27.82%Submissions: 809K+Points: 4Average Time: 59m
Given an array arr[]. Find the majority element in the array. If no majority element exists, return -1.

Note: A majority element in an array is an element that appears strictly more than arr.size()/2 times in the array.

Examples:

Input: arr[] = [1, 1, 2, 1, 3, 5, 1]
Output: 1
Explanation: Since, 1 is present more than 7/2 times, so it is the majority element.
Input: arr[] = [7]
Output: 7
Explanation: Since, 7 is single element and present more than 1/2 times, so it is the majority element.
Input: arr[] = [2, 13]
Output: -1
Explanation: Since, no element is present more than 2/2 times, so there is no majority element.
Constraints:
1 ≤ arr.size() ≤ 105
1 ≤ arr[i] ≤ 105


```
```
class Solution:
    def majorityElement(self, arr):
        #code here
        c=len(arr)/2
        l=len(arr)
        k={}
        o=0
        if l==1:
            return arr[0]
        elif l==2:
            return -1
        else:
            for i in arr:
                if i in k:
                    k[i]=k[i]+1
                else:
                    k[i]=1
        for n,ct in k.items():
            if ct>c:
                return n
        else:
            return -1
```
---

## new problem 3 ( Special Positions in a Binary Matrix )
```
Special Positions in a Binary Matrix
Given an m x n binary matrix mat, return the number of special positions in mat.

A position (i, j) is called special if mat[i][j] == 1 and all other elements in row i and column j are 0 (rows and columns are 0-indexed).

Input: mat = [[1,0,0],[0,0,1],[1,0,0]]
Output: 1
Explanation: (1, 2) is a special position because mat[1][2] == 1 and all other elements in row 1 and column 2 are 0.
Example 2:


Input: mat = [[1,0,0],[0,1,0],[0,0,1]]
Output: 3
Explanation: (0, 0), (1, 1) and (2, 2) are special positions.
 
Constraints:

m == mat.length
n == mat[i].length
1 <= m, n <= 100
mat[i][j] is either 0 or 1.
```
```
class Solution(object):
    def numSpecial(self, mat):
        """
        :type mat: List[List[int]]
        :rtype: int
        """
        m = len(mat)
        n = len(mat[0])
        r = [0] * m
        c = [0] * n
        for i, row in enumerate(mat):
            for j, v in enumerate(row):
                r[i] += v
                c[j] += v
        k = 0
        for i in range(m):
            for j in range(n):
                if mat[i][j] == 1 and r[i] == 1 and c[j] == 1:
                    k += 1
        return k

```
---

## new problem 4 Toeplitz matrix
```
Toeplitz matrix
Difficulty: EasyAccuracy: 49.05%Submissions: 50K+Points: 2
A Toeplitz matrix (also known as a diagonal-constant matrix) is a matrix in which every descending diagonal from left to right contains the same element.

Given a rectangular matrix mat, determine whether it is a Toeplitz matrix or not.
Implement the function isToeplitz(mat) that returns:

true if the matrix is a Toeplitz matrix
false otherwise
Examples:

Input: mat[][] = [[6, 7, 8],
                [4, 6, 7],
                [1, 4, 6]]
Output: true
Explanation: The matrix is Toeplitz because every diagonal from top-left to bottom-right has the same elements. 
For example, the main diagonal is 6 → 6 → 6, and other diagonals like 7 → 7 and 4 → 4 are also constant. 
Since all diagonals follow this pattern, the matrix is Toeplitz, so the output is true.
Input: mat[][] = [[6, 3, 8],
                [4, 9, 7],
                [1, 4, 6]]
Output: false
Explanation: The primary diagonal elements of the given matrix are [6, 9, 6]. As the diagonal elements are not same, the given matrix is not Toeplitz Matrix.
Constraints:
1 ≤ mat.size(), mat[0].size() ≤ 40
0 ≤ mat[i][j] ≤ 100
```
```
class Solution:
    def isToeplitz(self, mat):
        rows = len(mat)
        cols = len(mat[0])
        
        for i in range(1, rows):
            for j in range(1, cols):
                if mat[i][j] != mat[i-1][j-1]:
                    return False
        
        return True
```
---

## new problem 5 Minimum Distance to the Target Element
```
.Minimum Distance to the Target Element
Given an integer array nums (0-indexed) and two integers target and start, find an index i such that nums[i] == target and abs(i - start) is minimized. Note that abs(x) is the absolute value of x.

Return abs(i - start).

It is guaranteed that target exists in nums.

 

Example 1:

Input: nums = [1,2,3,4,5], target = 5, start = 3
Output: 1
Explanation: nums[4] = 5 is the only value equal to target, so the answer is abs(4 - 3) = 1.
Example 2:

Input: nums = [1], target = 1, start = 0
Output: 0
Explanation: nums[0] = 1 is the only value equal to target, so the answer is abs(0 - 0) = 0.
Example 3:

Input: nums = [1,1,1,1,1,1,1,1,1,1], target = 1, start = 0
Output: 0
Explanation: Every value of nums is 1, but nums[0] minimizes abs(i - start), which is abs(0 - 0) = 0.
 

Constraints:

1 <= nums.length <= 1000
1 <= nums[i] <= 104
0 <= start < nums.length
target is in nums.

```
```
class Solution:
    def getMinDistance(self, nums: List[int], target: int, start: int) -> int:
        l=len(nums)
        k=10**4
        for i in range(l):
            if nums[i]==target:
                k=min(abs(i-start),k)
        return k
```
---

## new problem 4 ( Check if Binary String Has at Most One Segment of Ones )
```
Check if Binary String Has at Most One Segment of Ones
Given a binary string s ​​​​​without leading zeros, return true​​​ if s contains at most one contiguous segment of ones. Otherwise, return false.

 

Example 1:

Input: s = "1001"
Output: false
Explanation: The ones do not form a contiguous segment.
Example 2:

Input: s = "110"
Output: true
 

Constraints:

1 <= s.length <= 100
s[i]​​​​ is either '0' or '1'.
s[0] is '1'.
```
```
class Solution(object):
    def checkOnesSegment(self, s):
        """
        :type s: str
        :rtype: bool
        """
        return '01' not in s
```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

## new problem
```

```
```

```
---

