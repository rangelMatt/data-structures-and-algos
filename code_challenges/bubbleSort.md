# Bubble Sort

## Problem Domain

Write a function that take in an array of integers and returns a sorted version of that array. Use the Bubble Sort algorithm to sort the array.

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

 is 8 <= 5 ?

  [5, 8, 2, 9, 5, 6, 3]

  is 8 <= 2 ?

  [5, 2, 8, 9, 5, 6, 3]

  is 8 <= 9 ?

  Yes! Move to next number 9.

  is 9 <= 5 ?

  [5, 2, 8, 5, 9, 6, 3]

  is 9 <= 6 ?

  [5, 2, 8, 5, 6, 9, 3]

  is 9 <= 3 ?

  [5, 2, 8, 5, 6, 3, 9]

  repeat till we sort through all integers of the array and return :
  [2, 3, 5, 5, 6, 8, 9]

```

### **algorithm**

while array is not sorted
iterate over array
check if element is greater or equal to the next element
if it is, swap elements
loop again until all elements are sorted from least to greatest

### **code**

```python
def bubbleSort(array):
  isSorted = False

  while not isSorted:
    for i in range(len(array) - 1):
      isSorted = True
      if array[i] > array[i + 1]:
        array[i], array[i + 1] = array[i + 1], array[i]
        isSorted False
  return array
```

### **testing**

check if array has strings
chick if array is there

### **BigO**

Space: `O(1)` because the algorithm is in constant space.

Time: `O(N^2)` because we are looping through the array multiple times until the array gets sorted.

### **Design Choice and Why**

Although there is a built in method, this is a good practice to learn to see what is going on within that method and build upon it and be specific if needed.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
