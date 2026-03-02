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

## new problem 3 (  )
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

