# Binary Search

## Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

### **input**

```python
nums = [-1,0,3,5,9,12]

target = 9
```

### **output**

```python
4
```

### **visual**

```python
target = 9

nums = [5,9,12]
        ^ ^  ^
        L M  R
```

### **algorithm**

While left is less or equal to right
check if the element in the middle is greater than the target
if it is, then look to the left of middle
else if, look to the right of middle
otherwise, we find the target value and now we return the index.

### **code**

```python
def search(nums, target):
left, right = 0, len(nums) - 1


  while left <= right:
    mid = left + ((right - left) // 2)

    if nums[mid] > target:
      right = mid - 1
    elif nums[mid] < target:
      left = mid + 1
    else:
      return mid

return -1
```

### **testing**

test for integers
test for strings
test for ascending integers
test for array

### **BigO**

Space & Time: O(log n), because we are dividing the array in half. We are doing this because we know that the values of the array are in an ascending order, so when we compare target to whats to the beginning of the array and at the end, this will tell us if we need to look to the left of the middle or the right of the middle. And then the other portion will not be looked at again.

### **Design Choice and Why**

Created with `O (log n)`, because that's what was being asked of in the problem domain. Also, it is a good practice, so when we encounter something like this int eh `wild`, we can sort the numbers and then eliminate half of the array to troubleshoot where are target is faster.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/binary-search)

-----

### 👈 [Back to Table of Contents](../toc.md)
