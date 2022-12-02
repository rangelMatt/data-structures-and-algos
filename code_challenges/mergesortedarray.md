# Merge Sorted Array

## **Problem Domain**

You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of elements in `nums` and `nums2` respectively.

Merge `nums1` and `nums2` into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array `nums1`. To accommodate this, `nums1` as a length of `m + n`, where the first `m` elements denote the elements that should be merged, and the last `n` elements are set to `0` and should be ignored. `nums2` has a length of `n`.

### **input**

nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3

### **output**

[1,2,2,3,5,6]

### **visual**

### **algorithm**

While there are elements in nums1 and nums2
find the largest value of nums1 and nums2
go to last position and replace it with nums1 of m
then decrement position in nums1
otherwise,
if nums2 is greater, replace with nums2 of n
then decrement position in nums2
decrement last position overall

if nums2 is longer than nums1
while nums 2 is longer
point last nums2 to last position of nums1

### **code**

```python

def merge(nums1, m, nums2, n):
last = m + n - 1

  while m > 0 and n > 0:
    if nums1[m - 1] > nums2[n - 1]:
      nums1[last] = nums1[m - 1]
      m -= 1
    else:
      nums1[last] = nums2[n - 1]
      n -= 1

  while n > 0:
    nums1[last] = nums2[n - 1]
    n, last = n - 1, last -1

  return nums1
```

### **testing**

test for empty arrays
test for strings
test for mixed elements
test for sorting/ascending numbers

### **BigO**

Space and Time: O(n), because we are going the length of the arrays by looking at each element of the arrays. So however long the length of the arrays, is how much time and space it will take.

### **Design Choice and Why**

Went with a brute force approach so I can wrap my head around data structures and algorithms again.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/merge-sorted-array)

-----

### 👈 [Back to Table of Contents](../toc.md)
