# Two Sum (Part Dux)

## Problem Domain

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

-

### **input**

#### 2 args

- nums: array of integers
- target: an integer

### **output**

- Array of indices

### **visual**

nums = [2,7,11,15], target = 9

i = 2
j = 7

if j == target - i

return [i, j]

output = [2, 7]

### **algorithm**

iterate over the nums array using enumerate method.
if target minus num is in the dictionary `lookup`
return the indices of the result of target - num in the dictionary, and index of nums
if not, assign index to dictionary `lookup` with value of num.

### **code**

```Python
def twoSum(nums, target):
  lookup = {}
  for i, n in enumerate(nums):
    if target - n in lookup:
      return [lookup[target - n], i]
    lookup[n] = i

  return []
```

### **testing**

test if there is an array
test if there are strings
test for length of array

### **BigO**

Time: O(n), because we are using enumerate to help assign keys to values which will aid us to subtract from target, so this is dependent on how large the array is.

Space: O(n), because this is dependent on how large the array is, we are storing keys and values within a dictionary in order to find the target.

### **Design Choice and Why**

I wanted to use enumerate, as I just came across that easy method, and I am very pleased at the result. I had pictured holding the keys and values in a dictionary which immediately led me to returning the indices that equal the target.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
