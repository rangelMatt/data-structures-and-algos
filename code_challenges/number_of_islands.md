# Number of Islands

## Problem Domain

Given an `m x n` 2d binary grid `grid` which represents a map of `1`s (land) and `0`s (water) return *the number of islands.*

An **island** is surrounded by water and is formed byu connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

### **input**

an array of arrays

### **output**

integer

### **visual**

```python
 # ["0","0","0","0","0"],
  # ["0","0","0","0","0"],
  # ["0","0","1","0","0"],
  # ["0","0","0","1","1"]
  islands = 0

  # 0,0: top, bottom, left, right
  # 1,0: top, bottom, left, right
  # 1,1: top, bottom, left, right
  # 0,1: top, bottom, left, right
  islands = 3 


```

### **algorithm**

set a counter for islands
iterate through the row of grid
iterate through the column of grid
check if current index row/column of the grid equals `1`
if it does, call helper function to reset current index to zero and iterate through top, bottom, left, right and grid to search for `1`,
once that has been reached, return and increment the counter
return islands count at the end.

### **code**

```python
class Solution:
 

  def dfs(self, grid, r, c):
    grid[r][c] = '0'
    lst = [(r-1, c), (r+1, c), (r, c-1), (r, c+1)]
    for row, col in lst:
      if row >= 0 and col >= 0 and row < len(grid) and col < len(grid[row]) and grid[row][col] == '1':
        self.dfs(grid, row, col)

  def numIslands(self, grid: List[List[str]]) -> int:
    islands = 0
    for r in range(len(grid)):
      for c in range(len(grid[r])):
        if grid[r][c] == '1':
          self.dfs(grid, r, c)
          islands += 1
    return islands
```

### **testing**

test for array of arrays
test for strings
test for letters in strings
test for integers

### **BigO**

Time = m x n, because we are looping through the entire grid.
Space = m x n, because we are storing the values as we evaluate them, so it would depend on how big the grid is.

### **Design Choice and Why**

Went with DFS as it was able to iterate through each index and flip index to `0` once it was already seen. That way, when we iterate through the whole array it recognizes there are no `1`s left in the array.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/number-of-islands/)

-----

### 👈 [Back to Table of Contents](../toc.md)
