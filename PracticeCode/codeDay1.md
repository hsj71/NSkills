## new problem 1
```
Indexes of Subarray Sum
Difficulty: MediumAccuracy: 16.5%Submissions: 1.9MPoints: 4Average Time: 20m
Given an array arr[] containing only non-negative integers, your task is to find a continuous subarray (a contiguous sequence of elements) whose sum equals a specified value target. You need to return the 1-based indices of the leftmost and rightmost elements of this subarray. You need to find the first subarray whose sum is equal to the target.

Note: If no such array is possible then, return [-1].

Examples:

Input: arr[] = [1, 2, 3, 7, 5], target = 12
Output: [2, 4]
Explanation: The sum of elements from 2nd to 4th position is 12.
Input: arr[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10], target = 15
Output: [1, 5]
Explanation: The sum of elements from 1st to 5th position is 15.
Input: arr[] = [5, 3, 4], target = 2
Output: [-1]
Explanation: There is no subarray with sum 2.
Constraints:
1 ≤ arr.size() ≤ 106
0 ≤ arr[i] ≤ 103
0 ≤ target ≤ 109
```
```
#User function Template for python3
class Solution:
    def subarraySum(self, arr, target):
        # code here
        l=0
        ck=0
        for i in range(len(arr)):
            ck=ck+arr[i]
            while ck>target:
                ck=ck-arr[l]
                l=l+1
            if ck==target:
                return [l+1,i+1]
        return [-1]
```
---

## new problem  2
```
Missing in Array
Difficulty: EasyAccuracy: 29.59%Submissions: 1.6MPoints: 2Average Time: 15m
You are given an array arr[] of size n - 1 that contains distinct integers in the range from 1 to n (inclusive). This array represents a permutation of the integers from 1 to n with one element missing. Your task is to identify and return the missing element.

Examples:

Input: arr[] = [1, 2, 3, 5]
Output: 4
Explanation: All the numbers from 1 to 5 are present except 4.
Input: arr[] = [8, 2, 4, 5, 3, 7, 1]
Output: 6
Explanation: All the numbers from 1 to 8 are present except 6.
Input: arr[] = [1]
Output: 2
Explanation: Only 1 is present so the missing element is 2.
Constraints:
1 ≤ arr.size() ≤ 106
1 ≤ arr[i] ≤ arr.size() + 1
```
```
class Solution:
    def missingNum(self, arr):
        # code here
        l=len(arr)+1
        sm=(l*(l+1))//2
        s=0
        for i in arr:
            s=s+i
        return sm-s
```
---

## new problem  3
```
Second Largest
Difficulty: EasyAccuracy: 26.72%Submissions: 1.4MPoints: 2Average Time: 15m
Given an array of positive integers arr[], return the second largest element from the array. If the second largest element doesn't exist then return -1.

Note: The second largest element should not be equal to the largest element.

Examples:

Input: arr[] = [12, 35, 1, 10, 34, 1]
Output: 34
Explanation: The largest element of the array is 35 and the second largest element is 34.
Input: arr[] = [10, 5, 10]
Output: 5
Explanation: The largest element of the array is 10 and the second largest element is 5.
Input: arr[] = [10, 10, 10]
Output: -1
Explanation: The largest element of the array is 10 and the second largest element does not exist.
Constraints:
2 ≤ arr.size() ≤ 105
1 ≤ arr[i] ≤ 105
```
```
class Solution:
    def getSecondLargest(self, arr):
        # Code Here
        l=-1
        sec=-1
        for i in arr:
            if i>l:
                sec=l
                l=i
            elif i>sec and i<l:
                sec=i
        return sec
                
```
---

## new problem  4
```
Kadane's Algorithm
Difficulty: MediumAccuracy: 36.28%Submissions: 1.2MPoints: 4Average Time: 20m
You are given an integer array arr[]. You need to find the maximum sum of a subarray (containing at least one element) in the array arr[].

Note : A subarray is a continuous part of an array.

Examples:

Input: arr[] = [2, 3, -8, 7, -1, 2, 3]
Output: 11
Explanation: The subarray [7, -1, 2, 3] has the largest sum 11.
Input: arr[] = [-2, -4]
Output: -2
Explanation: The subarray [-2] has the largest sum -2.
Input: arr[] = [5, 4, 1, 7, 8]
Output: 25
Explanation: The subarray [5, 4, 1, 7, 8] has the largest sum 25.
Constraints:
1 ≤ arr.size() ≤ 105
-104 ≤ arr[i] ≤ 104
```
```
class Solution:
    def maxSubarraySum(self, arr):
        # Code here
        ms=arr[0]
        cs=arr[0]
        for i in range(1,len(arr)):
            cs=max(arr[i],cs+arr[i])
            ms=max(ms,cs)
        return ms
```
---

## new problem  5
```
Minimum Jumps
Difficulty: MediumAccuracy: 11.91%Submissions: 1.1MPoints: 4
You are given an array arr[] of non-negative numbers. Each number tells you the maximum number of steps you can jump forward from that position.

For example:

If arr[i] = 3, you can jump to index i + 1, i + 2, or i + 3 from position i.
If arr[i] = 0, you cannot jump forward from that position.
Your task is to find the minimum number of jumps needed to move from the first position in the array to the last position.

Note:  Return -1 if you can't reach the end of the array.

Examples : 

Input: arr[] = [1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]
Output: 3 
Explanation: First jump from 1st element to 2nd element with value 3. From here we jump to 5th element with value 9, and from here we will jump to the last. 
Input: arr = [1, 4, 3, 2, 6, 7]
Output: 2 
Explanation: First we jump from the 1st to 2nd element and then jump to the last element.
Input: arr = [0, 10, 20]
Output: -1
Explanation: We cannot go anywhere from the 1st element.
Constraints:
2 ≤ arr.size() ≤ 105
0 ≤ arr[i] ≤ 105
```
```
class Solution:
	def minJumps(self, arr):
	    # code here
	    j, d, p = 0, 0, 0
        for i in range(len(arr)-1):
            d = max(d, i + arr[i])
            if(i >= d):
                return -1
            if(p == i):
                p = d
                j += 1
        return j
```
---

## new problem  6
```
Meeting Rooms
Difficulty: EasyAccuracy: 65.12%Submissions: 38K+Points: 2
Given a 2D array arr[][], where arr[i][0] is the starting time of ith meeting and arr[i][1] is the ending time of ith meeting, the task is to check if it is possible for a person to attend all the meetings such that he can attend only one meeting at a particular time.

Note: A person can attend a meeting if its starting time is greater than or equal to the previous meeting's ending time.

Examples:

Input: arr[][] = [[1, 4], [10, 15], [7, 10]]
Output: true
Explanation: Since all the meetings are held at different times, it is possible to attend all the meetings.
Input: arr[][] = [[2, 4], [9, 12], [6, 10]]
Output: false
Explanation: Since the second and third meeting overlap, a person cannot attend all the meetings.
Constraints:
1 ≤ arr.size() ≤ 105
0 ≤ arr[i] ≤ 2*106
```
```
class Solution:
    def canAttend(self, arr):
        # Code Here
        arr.sort(key=lambda x: x[0])
        for i in range(len(arr)-1):
            if(arr[i][1] > arr[i+1][0]):
                return False
        return True  
        
            
```
---

## new problem  7
```
190. Reverse Bits
Reverse bits of a given 32 bits signed integer.

Example 1:

Input: n = 43261596

Output: 964176192

Explanation:

Integer	Binary
43261596	00000010100101000001111010011100
964176192	00111001011110000010100101000000
Example 2:

Input: n = 2147483644

Output: 1073741822

Explanation:

Integer	Binary
2147483644	01111111111111111111111111111100
1073741822	00111111111111111111111111111110
 

Constraints:

0 <= n <= 231 - 2
n is even.
```
```
class Solution(object):
    def reverseBits(self, n):
        """
        :type n: int
        :rtype: int
        """
        k=0
        for i in range(32):
            k|= (n&1)<<(31-i)
            n>>=1
        return k

```
---

