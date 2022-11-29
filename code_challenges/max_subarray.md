# Max Subarray

## Problem Domain

Given an integer array `nums`, find the `*`subarray which as the largest sum and return its *sum*.

`*` subarray - a subarray is a contiguous non empty sequence of elements within an array.

### **input**

`nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]`

### **output**

`6`

### **visual**

```python

max_seen = 0
current_value = 0

nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]

current_value = current_value + `-2`

if (current_value) `-2` < 0:
  current_value = 0

if (max_seen)`0` < (current_value)`0`:
  max_seen = current_value

return (max_seen)`0` if (max_seen)`0` != 0 else max(nums)

```

### **algorithm**

Instantiate two pointers: max_seen and current_value
Search through each element of the array
Add the first element to current_value
Reset current_value to 0 if it is negative,
We will use max(nums) to found out the largest negative
Set max_seen to be current_value if current_value is positive, which we will keep track of
Return max_seen if it is not zero, otherwise, return largest single maximum number

### **code**

```Python
def maxSubArray(nums):

  max_seen = 0
  current_value = 0

  for num in nums: 
    current_value += num 

    if current_value < 0: 
      current_value = 0
    
    if max_seen < current_value:
      max_seen = current_value
  
  return max_seen if max_seen != 0 else max(nums)
```

### **testing**

Test if there are strings
Test if there are integers
Test if there is an array

### **BigO**

Space and Time: O(n), because this needs to traverse through the whole array once while comparing and adding values.

### **Design Choice and Why**

I feel this was a brute force solution in terms of adding and comparing numbers to get the max subarray.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
