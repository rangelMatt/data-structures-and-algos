# Contains Duplicate

## Problem Domain

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

### **input**

#### 1 argument, an array of integers

### **output**

#### boolean

### **visual**

hashTable = {}

nums = [1,2,3,1]

nums[i] = 1

hashTable = {1,2,3}
hashTable[nums[i]] = 1

return true

### **algorithm**

initialize hashtable
iterate over nums array
check if index at nums is not in hash table
assign key value pair to hash table
if index matches value
return true
if nums array doesn't have a matching pair
return false

### **code**

```python
hashTable = {}

for i in range(len(nums)):
  if nums[i] is not in hashTable:
    hashTable[nums[i]] = 1
  else: 
    return True
return False
```

### **testing**

Test if array exists
Test for strings
Test for length of array

### **BigO**

#### Time: O(n), because we are adding and searching for a pair of numbers using. This will take as many elements as the array has

### Space: O(n), because the space used by a hash table is linear with the number of elements in the hash table

### **Design Choice and Why**

I used a hash table to be able to store data and indicate whether the duplicate key value pair exists. This is done in constant time, which is used in many cases and will limit the time of searching. Meaning it's a relatively quick way to search.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/contains-duplicate/)

-----

### 👈 [Back to Table of Contents](../toc.md)
