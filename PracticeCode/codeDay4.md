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

# new code 3
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

