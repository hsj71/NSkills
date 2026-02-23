## new problem 1
```
Missing Element in Range
Difficulty: MediumAccuracy: 55.45%Submissions: 13K+Points: 4Average Time: 20m
Given an array arr[] of integers and a range [low, high], find all the numbers within the range that are not present in the array. return the missing numbers in sorted order.

Examples:

Input: arr[] = [10, 12, 11, 15], low = 10, high = 15
Output: [13, 14]
Explaination: Numbers 13 and 14 lie in the range [10, 15] but are not present in the array.
Input: arr[] = [1, 4, 11, 51, 15], low = 50, high = 55
Output: [50, 52, 53, 54, 55]
Explaination: Numbers 50, 52, 53, 54 and 55 lie in the range [50, 55] but are not present in the array.
Constraints:
1 ≤ arr.size(), low, high ≤ 105
1 ≤ arr[i] ≤ 105
```
```
class Solution:
    def missingRange(self, arr, low, high):
        new=[]
        s=set(arr)
        for i in range(low,high+1):
            if i not in s:
                new.append(i)
        return new
```
---

## new problem 2
```
Check If a String Contains All Binary Codes of Size K
Given a binary string s and an integer k, return true if every binary code of length k is a substring of s. Otherwise, return false.

Example 1:

Input: s = "00110110", k = 2
Output: true
Explanation: The binary codes of length 2 are "00", "01", "10" and "11". They can be all found as substrings at indices 0, 1, 3 and 2 respectively.
Example 2:

Input: s = "0110", k = 1
Output: true
Explanation: The binary codes of length 1 are "0" and "1", it is clear that both exist as a substring. 
Example 3:

Input: s = "0110", k = 2
Output: false
Explanation: The binary code "00" is of length 2 and does not exist in the array.
 

Constraints:

1 <= s.length <= 5 * 105
s[i] is either '0' or '1'.
1 <= k <= 20
```
```
class Solution:
    def hasAllCodes(self, s: str, k: int) -> bool:
        s2 = set()
        for i in range(len(s) - k + 1):
            s2.add(s[i : i + k] )
        return len(s2) == 1 << k
```
---

## new problem 1
```

```
```

```
---

## new problem 1
```

```
```

```
---

