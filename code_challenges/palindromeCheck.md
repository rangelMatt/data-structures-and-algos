# Palindrome Check

## Problem Domain

WRite a function that takes in a non-empty string and that returns a boolean representing whether the string is a palindrome.

### **input**

```python
string = "abcdcba"
```

### **output**

```python
True
```

### **visual**

```python

 V     V  True
"abcdcba"

  V   V   True
"abcdcba"

   V V   True
"abcdcba"

```

### **algorithm**

Create a couple of pointers.
Check first and lest points of the string
if they don't match, return false
if they do, repeat to next elements, second and second to last
repeat till true or false

### **code**

```python
def isPalindrome(string):
  leftIdx = 0
  rightIdx = len(string) - 1

  while leftIdx < rightIdx:
    if string[leftIdx] != string[rightIdx]
      return False
    leftIdx += 1
    rightIdx -= 1
  return True
```

### **testing**

Test for integers
Test for empty strings
Test for mixed

### **BigO**

Space is `O(1)`, because not storing anything, except for pointers.

Time is `O(n)`, because we are creating a new string while viewing the old string, which takes us twice as long to look.

### **Design Choice and Why**

Went with pointers as it doesn't hold string values for space, rather it uses pointers. This should prove to be slightly more efficient rather than storing strings or any other value in memory.

---

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

---

### 👈 [Back to Table of Contents](../toc.md)
