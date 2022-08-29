# Trees Height

## Problem Domain

There are `N` trees in Jon's backyard and height of tree `i` is `h[i]`. Jon doesn't like the appearance of it and is planning to increase and decrease the height of trees such that the new heights are in strictly increasing order. Every day he can pick one tree and increase or decrease the height by 1 unit. Heights can be 0 or even negative (it's a magical world).

Jon has guests coming after `X` days, hence he wants to know if it is possible to make heights strictly increasing in no more than `X` days?

### **input**

**First line**,Number of Trees: N<=2000, Number of Days: X<=5000

**Second Line**, `N` space separated integers where `ith` integer is `h[i]`

(N,X)

### **output**

YES or NO, if it is possible to make tree heights in strictly ascending order in no more than X days, if Yes, also print the number of days it will take.

### **visual**

### **algorithm**

### **code**

```Python
def solve(nums,X):
  N = len(nums)
  minn = min(nums)

  for i in range(len(nums)):
    nums[i] -= minn
  maxn = max(nums) + 1

  dp = [[float('inf')]*(maxn) for _ in range(N)]

  for j in range(maxn):
    dp[0][j] = abs(nums[0]-j)

  for i in range(1, len(nums)):
    min_so_far = min(dp[i-1][:i])
    for j in range(i, maxn):
      dp[i][j] = abs(nums[i]-j) + min_so_far
      min_so_far = min(min_so_far, dp[i-1][j])
  return "YES " + str(min(dp[-1])) if min(dp[-1]) <= X else "NO"
```

### **testing**

### **BigO**

### **Design Choice and Why**

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
