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
# new code 3 Furthest Point From Origin
```
Furthest Point From Origin
You are given a string moves of length n consisting only of characters 'L', 'R', and '_'. The string represents your movement on a number line starting from the origin 0.

In the ith move, you can choose one of the following directions:

move to the left if moves[i] = 'L' or moves[i] = '_'
move to the right if moves[i] = 'R' or moves[i] = '_'
Return the distance from the origin of the furthest point you can get to after n moves.

 

Example 1:

Input: moves = "L_RL__R"
Output: 3
Explanation: The furthest point we can reach from the origin 0 is point -3 through the following sequence of moves "LLRLLLR".
Example 2:

Input: moves = "_R__LL_"
Output: 5
Explanation: The furthest point we can reach from the origin 0 is point -5 through the following sequence of moves "LRLLLLL".
Example 3:

Input: moves = "_______"
Output: 7
Explanation: The furthest point we can reach from the origin 0 is point 7 through the following sequence of moves "RRRRRRR".
 

Constraints:

1 <= moves.length == n <= 50
moves consists only of characters 'L', 'R' and '_'.
```
```
class Solution:
    def furthestDistanceFromOrigin(self, moves: str) -> int:
        return abs(moves.count('L') - moves.count('R')) + moves.count('_')

```
---
# new code 4 Check if There is a Valid Path in a Grid
```
Check if There is a Valid Path in a Grid
You are given an m x n grid. Each cell of grid represents a street. The street of grid[i][j] can be:

1 which means a street connecting the left cell and the right cell.
2 which means a street connecting the upper cell and the lower cell.
3 which means a street connecting the left cell and the lower cell.
4 which means a street connecting the right cell and the lower cell.
5 which means a street connecting the left cell and the upper cell.
6 which means a street connecting the right cell and the upper cell.

You will initially start at the street of the upper-left cell (0, 0). A valid path in the grid is a path that starts from the upper left cell (0, 0) and ends at the bottom-right cell (m - 1, n - 1). The path should only follow the streets.

Notice that you are not allowed to change any street.

Return true if there is a valid path in the grid or false otherwise.

 

Example 1:


Input: grid = [[2,4,3],[6,5,2]]
Output: true
Explanation: As shown you can start at cell (0, 0) and visit all the cells of the grid to reach (m - 1, n - 1).
Example 2:


Input: grid = [[1,2,1],[1,2,1]]
Output: false
Explanation: As shown you the street at cell (0, 0) is not connected with any street of any other cell and you will get stuck at cell (0, 0)
Example 3:

Input: grid = [[1,1,2]]
Output: false
Explanation: You will get stuck at cell (0, 1) and you cannot reach cell (0, 2).
 

Constraints:

m == grid.length
n == grid[i].length
1 <= m, n <= 300
1 <= grid[i][j] <= 6
```
```
class Solution:
    def hasValidPath(self, grid: List[List[int]]) -> bool:
        m, n = len(grid), len(grid[0])
        p = list(range(m * n))

        def find(x):
            if p[x] != x:
                p[x] = find(p[x])
            return p[x]

        def left(i, j):
            if j > 0 and grid[i][j - 1] in (1, 4, 6):
                p[find(i * n + j)] = find(i * n + j - 1)

        def right(i, j):
            if j < n - 1 and grid[i][j + 1] in (1, 3, 5):
                p[find(i * n + j)] = find(i * n + j + 1)

        def up(i, j):
            if i > 0 and grid[i - 1][j] in (2, 3, 4):
                p[find(i * n + j)] = find((i - 1) * n + j)

        def down(i, j):
            if i < m - 1 and grid[i + 1][j] in (2, 5, 6):
                p[find(i * n + j)] = find((i + 1) * n + j)

        for i in range(m):
            for j in range(n):
                e = grid[i][j]
                if e == 1:
                    left(i, j)
                    right(i, j)
                elif e == 2:
                    up(i, j)
                    down(i, j)
                elif e == 3:
                    left(i, j)
                    down(i, j)
                elif e == 4:
                    right(i, j)
                    down(i, j)
                elif e == 5:
                    left(i, j)
                    up(i, j)
                else:
                    right(i, j)
                    up(i, j)
        return find(0) == find(m * n - 1)


```
---
# new code 1
```

```
```

```
---
