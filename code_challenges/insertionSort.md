# Insertion Sort

## Problem Domain

Write a function that takes in an array of integers and returns a sorted version of that array. Use the Insertion Sort algorithm to sort the array.

### **input**

```python
array = [8, 5, 2, 9, 5, 6, 3]
```

### **output**

```python
[2, 3, 5, 5, 6, 8, 9]
```

### **visual**

```python
 [8, 5, 2, 9, 5, 6, 3]
  if 5 is < 8:
    [5, 8, 2,...]

  if 2 is < 8:
    [5, 2, 8, ...]

  if 2 is < 5:
    [2, 5, 8,...]

```

### **algorithm**

iterate over the array
while we are passed the first element,
we compare elements of the array
if they are lesser than the compared number,
swap the lesser to the left of the comparison
return the array.

### **code**

```python
def insertionSort(array):
  for i in range(1, len(array)):
    j = i
    while j > 0 and array[j] < array[j - 1]
      swap(j, j - 1, array)
      j -= 1
  return array

def swap(i, j, array)
  array[i], array[j] = array[j], array[i]

```

### **testing**

test for strings
test if array is empty
test for mixed elements

### **BigO**

Space is `O(1)`, constant space because the algorithm had occurred in place within the array.
Time is `O(n^2)`, because we have to do a bunch of comparisons and swaps, depending on the length of the array.

### **Design Choice and Why**

Used two loops, the for loops' intention is to loop through the array once. And then we enter the while loop that will be evaluating each element and swapping the lesser number to the front of the array.

---

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

---

### 👈 [Back to Table of Contents](../toc.md)
