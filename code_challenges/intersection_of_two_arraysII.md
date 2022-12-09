# Intersection of Two Arrays II

## Problem Domain

Given two integer arrays `nums1` and `nums2`, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.

### **input**

```python
nums1 = [1, 2, 2, 1], nums2 = [2, 2]
```

### **output**

```python
[2, 2]
```

### **visual**

```python
nums2 = [2, 2]
nums1 = [1, 2, 2, 1]
            ^
     nums2 =2 + 1 > 0

output = [2]
```

### **algorithm**

set a counter for nums1
set and output
iterate over nums2
if the counter of n is greater than zero
append that to output
then decrease counter by 1, which eliminates duplicating numbers that don't appear as many times
return the output

### **code**

```python
c = Counter(nums1)
output = []

for n in nums2:
  if c[n] > 0:
    output.append(n)
    c[n] -= 1

return output
```

### **testing**

test for strings
test for empty arrays

### **BigO**

Space and Time: O(n), because we are going the length of the arrays by looking at each element of the arrays. And also counting the number of times the number is there. So that would add another element to the space and time. I did a brief search and I believe it is more of a `O(n + m)`, where m is the count of times the number appears.

### **Design Choice and Why**

This is more of a brute force function to count how many times a number is repeated in each array. Doing this which helps me wrap my head around DSA's.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/intersection-of-two-arrays-ii/)

-----

### 👈 [Back to Table of Contents](../toc.md)
