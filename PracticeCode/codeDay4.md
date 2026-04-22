# new code 1 URLify a given string
```
URLify a given string
Given a string s, replace all the spaces in the string with '%20'.

Examples:

Input: s = "i love programming"
Output: "i%20love%20programming"
Explanation: The 2 spaces are replaced by '%20'
Input: s = "Mr Benedict Cumberbatch"
Output: "Mr%20Benedict%20Cumberbatch"
Explanation: The 2 spaces are replaced by '%20'
Constraints:
1 ≤ s.size() ≤ 104
```
```
class Solution:
    def URLify(self, s): 
        # code here
        result = ""
        for ch in s:
            if ch == " ":
                result += "%20"
            else:
                result += ch
                
        return result

```
---

# new code 2  Anagram Palindrome
```
Anagram Palindrome
Given a string s, determine whether its characters can be rearranged to form a palindrome. Return true if it is possible to rearrange the string into a palindrome; otherwise, return false.

Examples

Input: s = "baba"
Output: true
Explanation: Can be rearranged to form a palindrome "abba" 
Input: s = "geeksogeeks"
Output: true
Explanation: The characters of the string can be rearranged to form the palindrome "geeksoskeeg".
Input: s = "geeksforgeeks"
Output: false
Explanation: The given string can't be converted into a palindrome.
Constraints:
1 ≤ s.length ≤ 106
s consists of only lowercase English letters.
```
```
class Solution:
    def canFormPalindrome(self, s):
        # code here
        freq = {}
        for ch in s:
            if ch in freq:
                freq[ch] += 1
            else:
                freq[ch] = 1 
        is_odd=0
        for val in freq.values():
            if val&1==1:
                is_odd+=1
        return is_odd<2
```
---

# new code 3 You are given an integer n.
```
You are given an integer n.

Define its mirror distance as: abs(n - reverse(n))​​​​​​​ where reverse(n) is the integer formed by reversing the digits of n.

Return an integer denoting the mirror distance of n​​​​​​​.

abs(x) denotes the absolute value of x.

 

Example 1:

Input: n = 25

Output: 27

Explanation:

reverse(25) = 52.
Thus, the answer is abs(25 - 52) = 27.
Example 2:

Input: n = 10

Output: 9

Explanation:

reverse(10) = 01 which is 1.
Thus, the answer is abs(10 - 1) = 9.
Example 3:

Input: n = 7

Output: 0

Explanation:

reverse(7) = 7.
Thus, the answer is abs(7 - 7) = 0.
```
```
class Solution:
    def mirrorDistance(self, n: int) -> int:
        o = n
        r = 0
        while (n > 0):
            digit = n % 10
            r = r * 10 + digit
            n = floor(n / 10)

        return abs(o - r)

```
---

# new code 4 Check for Power
```
Check for Power
Given two positive integers x and y, determine if y is a power of x. If y is a power of x, return true. Otherwise, return false.

Examples:

Input: x = 2, y = 8
Output: true 
Explanation: 23 is equal to 8.
Input: x = 1, y = 8
Output: false
Explanation: Any power of 1 is not equal to 8.
Input: x = 46, y = 205962976
Output: true
Explanation: 465 is equal to 205962976.
Input: x = 50, y = 312500000
Output: true
Explanation: 505 is equal to 312500000.
Constraints:
1 ≤ x ≤ 103
1 ≤ y ≤ 109
```
```
class Solution:
    def isPower(self, x, y):
        if x == 1:
            return y == 1
        while y % x == 0:
            y = y // x
            
        return y == 1
```
---

# new code 5  Mean of range in array
```
Mean of range in array
Given an integer array arr[] and a 2D array queries[][]. Each query queries[i] = [l, r] represents a subarray ranging from index l to r (inclusive). For every query, compute the mean (average) of the elements in the specified range, and return the floor value of that mean.

Return an array where each element corresponds to the result of a query.

Examples:

Input: arr[] = [1, 2, 3, 4, 5], queries[][] = [[0, 2], [1, 3], [0, 4]]
Output: [2, 3, 3]
Explanation: The array is [1, 2, 3, 4, 5].
Query 1: l = 0, r = 2 → subarray [1, 2, 3] → sum = 6 → mean = 6/3 = 2
Query 2: l = 1, r = 3 → subarray [2, 3, 4] → sum = 9 → mean = 9/3 = 3
Query 3: l = 0, r = 4 → subarray [1, 2, 3, 4, 5] → sum = 15 → mean = 15/5 = 3
Hence the answer is [2, 3, 3]
Input: arr[] = [6, 7, 8, 10], queries[][] = [[0, 3], [1, 2]]
Output: [7, 7]
Explanation: The array is [6, 7, 8, 10].
Query 1: l = 0, r = 3 → subarray [6, 7, 8, 10] → sum = 31 → mean = 31/4 = 7 (floor value)
Query 1: l = 1, r = 2 → subarray [7, 8] → sum = 15 → mean = 15/2 = 7 (floor value)
Hence the answer is [7, 7]
Constraints: 
1 ≤ arr.size() ≤ 105
1 ≤ arr[i] ≤ 103
1 ≤ queries.size() ≤ 105
1 ≤ queries[i][0] ≤ queries[i][1] < arr.size()
```
```
class Solution:
    def findMean(self, arr, queries):
        # code here
        ans = []
        n = len(arr)
        prefix = [0] * n
        prefix[0] = arr[0]
        for i in range(1, n):
            prefix[i] = prefix[i-1] + arr[i]
        
        for r in queries:
            Sum = prefix[r[1]] - (prefix[r[0] - 1] if r[0] > 0 else 0)
            ans.append(Sum // (r[1] - r[0] + 1))
        return ans
```
---

